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
            <svg fill="#ffffff" width="32px" height="32px" viewBox="0 0 94.926 94.926">
                <g>
                    <path d="M55.931,47.463L94.306,9.09c0.826-0.827,0.826-2.167,0-2.994L88.833,0.62C88.436,0.224,87.896,0,87.335,0
		c-0.562,0-1.101,0.224-1.498,0.62L47.463,38.994L9.089,0.62c-0.795-0.795-2.202-0.794-2.995,0L0.622,6.096
		c-0.827,0.827-0.827,2.167,0,2.994l38.374,38.373L0.622,85.836c-0.827,0.827-0.827,2.167,0,2.994l5.473,5.476
		c0.397,0.396,0.936,0.62,1.498,0.62s1.1-0.224,1.497-0.62l38.374-38.374l38.374,38.374c0.397,0.396,0.937,0.62,1.498,0.62
		s1.101-0.224,1.498-0.62l5.473-5.476c0.826-0.827,0.826-2.167,0-2.994L55.931,47.463z"/>
                </g>
            </svg>
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