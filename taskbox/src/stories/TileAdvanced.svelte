<script>
    import TileSingle from "./TileSingle.svelte";
    import TileMedia from "./TileMedia.svelte";

    export let name = "Media name";
    export let src;
    export let text;
    export let even;

</script>

<div class={even ? "container" :"container-reverse"}>
    <TileMedia media_type="image" src={src} name={name}/>
    <TileSingle text={text}/>
</div>

<style>


    .container {
        background-color: var(--section-bg);
        border-radius: 10px;
    }

    .container-reverse {
        background-color: var(--section-bg);
        border-radius: 10px;
    }

    @media screen and (min-width: 900px) {
        .container {
            display: flex;
            flex-direction: row;
        }

        .container-reverse {
            display: flex;
            flex-direction: row-reverse;
        }
    }
</style>
