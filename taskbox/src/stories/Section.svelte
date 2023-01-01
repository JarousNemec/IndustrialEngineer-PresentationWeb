<script>

    import TileSingle from "./TileSingle.svelte";
    import TileAdvanced from "./TileAdvanced.svelte";
    import TileMedia from "./TileMedia.svelte";

    export let section_name
    export let single_tile_data = [];
    export let advanced_tile_data = [];
    export let media_tile_data = [];

    function isEven(index) {
        return index % 2 === 0
    }

</script>

<div class="container">
    <h3>{section_name}</h3>

    <div class="grid-container">
        {#each single_tile_data as {text}, index}

            <TileSingle text={text} even="{isEven(index)}"/>
        {/each}
    </div>
    <div class="grid-container">
        {#each advanced_tile_data as {image, text}, index}
            <TileAdvanced image={image} text={text} even="{isEven(index)}"/>
        {/each}
    </div>
    <div class="media-grid-container">
        {#each media_tile_data as {src, media_type}, index}
            <TileMedia src={src} media_type={media_type} even="{isEven(index)}"/>
        {/each}
    </div>
</div>

<style>

    .container {
        text-align: center;
        margin: 1em;
    }

    .grid-container {
        display: flex;
        flex-direction: column;
        width: 100%;
        gap: 10px;
    }


    .media-grid-container {
        display: flex;
        flex-flow: row wrap;
        justify-content: space-around;
        margin: 0 auto;
        grid-gap: 10px;
        width: 100%;
    }

    /* On screens that are 992px or less, set the background color to blue */
    @media screen and (max-width: 992px) {
        .grid-container {
            background-color: blue;
        }
    }

    /* On screens that are 600px or less, set the background color to olive */
    @media screen and (max-width: 600px) {
        .grid-container {
            background-color: olive;
        }
    }


</style>