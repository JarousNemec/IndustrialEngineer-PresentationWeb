<script>
    import TileSingle from "./TileSingle.svelte";
    import TileMedia from "./TileMedia.svelte";

    export let image;
    export let text;
    export let even;

</script>

    <div class={even ? "container" :"container-reverse"}>
        <TileMedia media_type="image" src={image}/>
        <TileSingle text={text}/>
    </div>

<style>

    .container {
        background-color: var(--section-bg);
        display: flex;
        flex-direction: row;
    }

    .container-reverse {
        background-color: var(--section-bg);
        display: flex;
        flex-direction: row-reverse;
    }
</style>
