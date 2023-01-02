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
    <h2>{section_name}</h2>

    <div class="grid-container">
        {#each single_tile_data as {text}, index}
            <TileSingle id={index} text={text} even="{isEven(index)}"/>
        {/each}
    </div>
    <div class="grid-container">
        {#each advanced_tile_data as {name, src, text}, index}
            <div>
                <TileAdvanced name={name} src={src} text={text} even="{isEven(index)}"/>
            </div>
        {/each}
    </div>
    <div class="media-container">

        {#each media_tile_data as {name, src, media_type}, index}
            <TileMedia name={name} src={src} media_type={media_type} even="{isEven(index)}"/>
        {/each}
        <div class="space"></div>
        <div class="space"></div>
    </div>
</div>
<style>

    .container {
        text-align: center;
        margin: 1em;
    }

    @font-face {
        font-family: mainThemeFont;
        src: url("./assets/font/The Foregen Rough One.ttf");
    }

    h2 {
        font-family: mainThemeFont, serif;
        color: var(--label-text);
    }

    .grid-container {
        display: flex;
        flex-direction: column;
        width: 100%;
        gap: 10px;
    }

    .space {
        min-width: 250px;
        row-gap: 10px;
        margin: 0 10px;
    }

    .media-container {

        display: flex;
        flex-direction: row;
        justify-content: center;
        flex-wrap: wrap;

        margin: auto;
        grid-gap: 28px;
        width: 100%;
    }
</style>


