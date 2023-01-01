<script>
    import TileSingle from "./TileSingle.svelte";
    import TileMedia from "./TileMedia.svelte";

    export let src;
    export let text;
    export let even;

</script>

    <div class={even ? "container" :"container-reverse"}>
        <TileMedia media_type="image" src={src}/>
        <TileSingle text={text}/>
    </div>

<style>

    .container {
        background-color: var(--section-bg);
        display: flex;
        flex-direction: row;
        border-radius: 10px;
    }

    .container-reverse {
        background-color: var(--section-bg);
        display: flex;
        flex-direction: row-reverse;
        border-radius: 10px;
    }
</style>
