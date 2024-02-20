<script lang="ts">
    import '$lib/style.css'
</script>

<header>
    <h3>
        <a href="/">Barcode Print POC</a>
    </h3>
</header>
<main>
    <slot/>
</main>

<style>
    header {
        font-weight: 400;
        padding: 1rem 2rem;
        background: #eee;
    }

    main {
        padding: 2rem;
    }

    main > :global(h1) {
        margin-bottom: 1rem;
    }
</style>