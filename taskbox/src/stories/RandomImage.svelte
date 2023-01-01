<script>
    import {fade} from 'svelte/transition'

    export let src;
    export let clicked = false;
    export let media_type;
    let movie = (media_type === 'movie')
</script>
<div class="container">
    {#if movie}
        <video class="image">
            <source src={src} type="video/mp4">
            <source src={src} type="video/ogg">
            Your browser does not support the video tag.
        </video>
    {:else }
        <img class="image" loading="lazy" on:click={()=>{
	clicked = !clicked;
}} src={src} crossorigin="anonymous" alt="random img"/>
    {/if}
</div>

{#if clicked}
    <div class="modal" transition:fade={{duration: 100}}>
        <div on:click={()=>{clicked = !clicked}} class="close">
            x
        </div>
        {#if movie}
            <video width="320" height="240" controls>
                <source src={src} type="video/mp4">
                <source src={src} type="video/ogg">
                Your browser does not support the video tag.
            </video>
        {:else }
            <div class="modal-image">
                <img class="m-image" loading="lazy" src={src} alt="random img"/>
            </div>
        {/if}

    </div>
{/if}
<style>
    .m-image {
        width: 100%;
        height: auto;
        max-height: 600px;
        object-fit: scale-down;
    }

    .close {
        cursor: pointer;
        font-size: 3rem;
        position: absolute;
        right: 0;
        color: white;
        margin-right: 1.5rem;
        top: 0;
    }

    .image {
        margin-top: auto;
        margin-bottom: auto;
        cursor: pointer;
        max-width: 200px;
        max-height: 200px;
        transition: 0.125s;

        position: absolute;

        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);

    }

    .image:hover {
        opacity: 0.7;
    }

    img:active {
        opacity: 0.5;
    }

    .modal-image {
        margin: auto;
        display: block;
        width: 80%;
        max-width: 100%;
    }

    .modal {
        position: fixed;
        z-index: 2;
        padding-top: 100px;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        overflow: auto;
        background-color: rgb(0, 0, 0);
        background-color: rgba(0, 0, 0, 0.9);
    }
</style>