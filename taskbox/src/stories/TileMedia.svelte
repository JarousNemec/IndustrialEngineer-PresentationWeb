<script>

    import ModalDialog from './ModalDialog.svelte';

    let showModal = false;

    export let src;
    export let media_type; // image, movie
    let movie = (media_type == 'movie')

    function close() {
        showModal = false
    }

</script>


<tile>
    <div class="container">
        <img src={src} alt="" class="{media_type === 'movie' ? 'mask center_image ' : 'center_image'}"
             on:click="{() => showModal = true}">
        {#if showModal}
            <ModalDialog close_callback={close} on:close="{() => showModal = false}"/>
        {/if}
    </div>
</tile>


<style>
    .container {
        border: solid 2px #66bf3c;
        border-radius: 10px;
        max-height: 250px;
        max-width: 250px;
    }

    .center_image {
        display: block;
        height: 200px;
        width: 200px;
        margin-left: auto;
        margin-right: auto;
    }


    .mask {
        background-color: #ae762d;
        opacity: 0.8;
        -webkit-mask: url("./assets/images/movie-videos-icon.svg") no-repeat center;
        mask: url("./assets/images/movie-videos-icon.svg") no-repeat center;
    }

</style>
