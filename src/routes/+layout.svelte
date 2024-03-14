<script>
    const nav = [
        {
            title: "Nature",
            href: "/nature",
        },
        {
            title: "Animals",
            href: "/animals",
        },
        {
            title: "Architecture",
            href: "/architecture",
        },
        {
            title: "People",
            href: "/people",
        },
        {
            title: "temp",
            href: "/temp",
        },
    ];
</script>

<nav>
    <div class="nav-container">
        <a href="/" class="nav-logo" title="Back to Homepage">Gallery Name</a>
        <div class="nav-links">
            {#each nav as link}
                <a href={link.href} class="link">{link.title}</a>
            {/each}
        </div>
    </div>
</nav>
<div class="container">
    <!-- Images will be displayed below -->
    <slot />
</div>

<style>
    .container {
        max-width: 1400px;
        margin: 50px auto;
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
        gap: 20px;
    }

    nav {
        background-color: #f9f9f9; 
        padding: 15px; 
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); 
    }

    .nav-logo {
        font-size: 26px; 
        font-weight: bold;
        text-decoration: none;
        color: #000000; 
    }

    .nav-links {
        display: flex;
        justify-content: space-between; 
    }

    .link {
        margin-left: 15px; 
        color: #666; 
        text-decoration: none;
    }
</style>
