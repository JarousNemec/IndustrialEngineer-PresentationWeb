<script>
    import RandomImage from "./RandomImage.svelte";

    export let src;
    export let media_type; // image, movie
    let movie = (media_type === 'movie')
    let media_source;
    let type;
</script>

<div class="container">
    <div class="label">Media name</div>
    <div class="img-overlay-wrap" >
        {#if movie}
            <svg viewBox="0 0 472.615 472.615">
                <g>
                    <g>
                        <path d="M236.308,0C105.799,0,0,105.798,0,236.308c0,130.507,105.799,236.308,236.308,236.308s236.308-105.801,236.308-236.308 C472.615,105.798,366.816,0,236.308,0z M139.346,347.733V124.88l229.37,111.428L139.346,347.733z"/>
                    </g>
                </g>
            </svg>
            <RandomImage class="img-overlay-wrap bordered" src={src}/>
        {:else}
            <RandomImage class="img-overlay-wrap " src={src}/>
        {/if}
    </div>

</div>

<style>
    .container {
        text-align: center;
        background-color: var(--section-bg);
        border-radius: 10px;
        display: grid;
        gap: 10px;
        padding: 10px;
        justify-content: center;
    }

    .label {
        font-family: mainThemeFont, serif;
        color: var(--label-text);
        margin-top: 5px;
    }

    .img-overlay-wrap {
        position: relative;
        display: inline-block;
        transition: transform 10ms ease-in-out;

        cursor: pointer;
        border-radius: 10px;

        height: 200px;
        width: 250px;
    }

    .bordered {
        box-sizing: border-box;
        -moz-box-sizing: border-box;
        -webkit-box-sizing: border-box;
        border-style: solid;
        border-width: 10px;
        border-color: black;
    }


    .img-overlay-wrap  { /* <= optional, for responsiveness */
        width: 100%;
        height: 100%;
        border-radius: 20px;
    }

    .img-overlay-wrap svg {
        position: absolute;

        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);

        height: 50%;
        width: 50%;
    }
</style>
