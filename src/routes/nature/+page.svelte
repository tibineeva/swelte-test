<!-- Nature.svelte -->
<script>
    let images = ['nature1.jpg', 'nature2.jpg', 'nature3.jpg'];
    let currentImage = 0;

    function nextImage() {
        currentImage = (currentImage + 1) % images.length;
    }

    function prevImage() {
        currentImage = (currentImage - 1 + images.length) % images.length;
    }
</script>

<h1>Nature</h1>

<div class="gallery">
    <img src={images[currentImage]} alt="Nature Image" />

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
