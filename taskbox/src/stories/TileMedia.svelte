<script>

    import ModalDialog from './ModalDialog.svelte';

    let showModal = false;

    export let image;
    export let media_type;

    function close() {
        showModal = false
    }

</script>


<tile>
    <div class="container">
        <img src="./assets/coffee.png" alt="Rockss" class="image" on:click="{() => showModal = true}">

    </div>

    {#if showModal}
        <ModalDialog close_callback={close} on:close="{() => showModal = false}"/>
    {/if}

</tile>


<style>
    .container {
        border: solid 2px #66bf3c;
        border-radius: 10px;
        margin-left: 10px;
    }

    .image {
        height: 200px;
        width: 200px;
    }

</style>
