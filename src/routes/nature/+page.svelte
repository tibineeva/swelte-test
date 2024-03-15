<!-- Nature.svelte -->
<script>
    let images = [
        {
            src: 'https://art-dot.ru/wp-content/uploads/2020/10/klod-mone-rybatskii-domik-v-varanzh-vile.jpg',
            alt: 'Рыбацкий домик в Варанж-Виле',
            caption: 'Клод Моне]'
        },
        {
            src: 'https://art-dot.ru/wp-content/uploads/2020/10/ivan-shishkin-utro-v-sosnovom-lesu.jpg',
            alt: 'Утро в сосновом лесу',
            caption: 'Иван Шишкин'
        },
        {
            src: 'https://art-dot.ru/wp-content/uploads/2020/10/andrei-martynov-narodnye-gulyaniya-v-dvortsovom-parke-pod-sankt-peterburgom.jpg',
            alt: 'Народные гуляния в дворцовом парке под Санкт-Петербургом',
            caption: 'Андрей Мартынов'
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

<h1>Nature Gallery</h1>

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
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .navigation {
        margin-top: 20px;
    }
</style>
