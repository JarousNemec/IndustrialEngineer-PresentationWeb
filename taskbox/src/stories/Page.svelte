<script>
    import './page.css';
    import Layout from "./Layout.svelte";
    export let name;
    export let backgroundImage;
</script>

<svelte:head>
    <title>{name}</title>
</svelte:head>

<div class="container" style="--image: url({backgroundImage});">
    <Layout/>
</div>
<style>

    .container {
        background: linear-gradient( rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6) ), var(--image);
        background-color: var(--page-bg);
        background-repeat: repeat;
        width: 100vw;
        height: 100vh;
    }

    :global(body) {
        padding: 0;
    }
</style>