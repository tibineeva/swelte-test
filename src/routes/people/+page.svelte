<!-- People.svelte -->
<script>
    let images = [
        {
            src: 'https://upload.wikimedia.org/wikipedia/commons/8/89/Happy_Lovers.jpg',
            alt: 'Beautiful People Image 1',
            caption: 'Счастливые любовники — Франсуа Буше'
        },
        {
            src: 'https://k-a-r-t-i-n-a.ru/wp-content/uploads/2023/11/analiz-kartiny-rafaelya-santi-dama-s-edinorogom.jpg',
            alt: 'Beautiful People Image 2',
            caption: 'Дама с единорогом — Рафаэль Санти'
        },
        {
            src: 'https://artifex.ru/wp-content/uploads/2017/02/%D0%96%D0%B8%D0%B2%D0%BE%D0%BF%D0%B8%D1%81%D1%8C_%D0%AF%D0%BD-%D0%92%D0%B5%D1%80%D0%BC%D0%B5%D0%B5%D1%80_%D0%94%D0%B5%D0%B2%D1%83%D1%88%D0%BA%D0%B0-%D1%81-%D0%B6%D0%B5%D0%BC%D1%87%D1%83%D0%B6%D0%BD%D0%BE%D0%B8-%D1%81%D0%B5%D1%80%D0%B5%D0%B6%D0%BA%D0%BE%D0%B8-1665.jpg',
            alt: 'Beautiful People Image 3',
            caption: 'Девушка с жемчужной сережкой — Ян Вермеер'
        }
    ];

    let currentImage = 0;

    function nextImage() {
        currentImage = (currentImage + 1) % images.length;
    }

    function prevImage() {
        currentImage = (currentImage - 1 + images.length) % images.length;
    }
</script>

<h1>People Gallery</h1>

<div class="gallery">
    <a href={images[currentImage].src}>
        <img src={images[currentImage].src} alt={images[currentImage].alt} />
    </a>
    
    <p>{images[currentImage].caption}</p>

    <div class="navigation">
        <button on:click={prevImage}>Previous</button>
        <button on:click={nextImage}>Next</button>
    </div>
</div>

<style>
    .gallery {
        text-align: center;
        margin-top: 20px;
        background-color: #f9f9f9; /* Цвет фона */
        padding: 20px; /* Поля вокруг галереи */
        border-radius: 10px; /* Закругленные углы */
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); /* Тень */
        transition: background-color 0.3s; /* Анимация изменения цвета фона */
    }

    .gallery:hover {
        background-color: #e9e9e9; /* Цвет фона при наведении курсора */
    }

    .gallery img {
        max-width: 100%;
        height: auto;
        border: 2px solid #333;
        border-radius: 5px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        margin-bottom: 10px;
        transition: transform 0.3s; /* Анимация при наведении на изображение */
    }

    .gallery img:hover {
        transform: scale(1.1); /* Увеличение изображения при наведении */
    }

    .gallery p {
        font-style: italic;
        font-size: 14px;
    }

    .navigation {
        margin-top: 20px;
    }

    .navigation button {
        padding: 5px 10px;
        margin: 0 5px;
        background-color: #333;
        color: #fff;
        border: none;
        border-radius: 3px;
        cursor: pointer;
    }

    .navigation button:hover {
        background-color: #555;
    }

    h1 {
        font-size: 36px; /* Увеличение размера текста */
        color: #333; /* Цвет текста */
        text-transform: uppercase; /* Преобразование текста в верхний регистр */
        text-shadow: 2px 2px 2px rgba(0, 0, 0, 0.2); /* Тень текста */
    }
</style>
