<!-- Architecture.svelte -->
<script>
    let images = [
        {
            src: 'https://arthive.net/res/media/img/oy1000/work/4ff/186700@2x.webp',
            alt: 'Beautiful Architecture Image 1',
            caption: 'Водопад — Мауриц Корнелис Эшер'
        },
        {
            src: 'https://arthive.net/res/media/img/orig/work/8ad/521187@2x.webp',
            alt: 'Beautiful Architecture Image 2',
            caption: 'Руанский собор вечером — Клод Моне'
        },
        {
            src: 'https://arthive.net/res/media/img/orig/work/df8/647357@2x.webp',
            alt: 'Beautiful Architecture Image 3',
            caption: 'Меланхолия и тайна улицы— Джорджо де Кирико'
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

<h1>Architecture Gallery</h1>

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
