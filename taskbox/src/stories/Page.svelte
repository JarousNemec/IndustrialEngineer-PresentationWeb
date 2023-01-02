<script>
    import './page.css';
    import Layout from "./Layout.svelte";
    import {page_title} from "./assets/Layout_data.json";
    import {background_image} from "./assets/Layout_data.json";

    export let backgroundImage;
</script>

<svelte:head>
    <title>{page_title}</title>
</svelte:head>

<div class="container" style="--image: url({background_image});">
    <Layout/>
</div>
<style>

    .container {
        background: linear-gradient( rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6) ), var(--image);
        background-color: var(--page-bg);
    }

    :global(body) {
        padding: 0;
    }
</style>