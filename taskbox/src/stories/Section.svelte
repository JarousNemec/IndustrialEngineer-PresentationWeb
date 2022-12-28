<script>

    import Tile from "./Tile.svelte";

    export let section_name

    export let names = [{image: 1, text: 'Name 1'},{image: 2, text: 'Name 2'},{image: 3, text: 'Name 3'}];

</script>


<centerlayout >
    <div class="container">
    <h3>{section_name}</h3>
    <div class="grid-container">
        {#each names as {image, text}, index}
            <Tile image={image}  text={text} />
        {/each}
    </div>
    </div>

</centerlayout>


<style>

    .container {
        border: 2px solid #1ea7fd;
        text-align: center;
    }

    .grid-container {
        display: flex;
        flex-direction: column;

        width: 800px;
        margin: 0 auto;

        background-color: dimgray;
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