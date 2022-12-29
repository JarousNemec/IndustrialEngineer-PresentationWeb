<script>
    import './page.css';
    import Layout from "./Layout.svelte";
    export let name = "Page"
    export let backgroundImage = "./assets/bg-image.png";
</script>

<svelte:head>
    <title>{name}</title>
</svelte:head>

<div class="container" style="--image: url({backgroundImage});">
    <Layout/>
</div>
<style>

    .container::before {
        background-image: var(--image);
        background-color: var(--page-bg);
        width: 100vw;
        height: 100vh;
    }

    :global(body) {
        padding: 0;
    }
</style>