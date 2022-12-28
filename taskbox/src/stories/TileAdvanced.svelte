<script>

    import ModalDialog from './ModalDialog.svelte';
    import TileSingle from "./TileSingle.svelte";

    let showModal = false;

    export let image;
    export let text;
    export let even;

    function close() {
        showModal = false
    }

</script>


<tile>
    <div class={even ? "container" :"container-reverse"}>
        <TileSingle text={text}/>
        <img src="./assets/coffee.png" alt="Rockss" class="image" on:click="{() => showModal = true}">
    </div>

    {#if showModal}
        <ModalDialog close_callback={close} on:close="{() => showModal = false}"/>
    {/if}

</tile>


<style>
    .image {
        height: 100px;
        width: 120px;
    }

    .container {
        display: flex;
        flex-direction: row;
    }

    .container-reverse {
        display: flex;
        flex-direction: row-reverse;
    }

</style>
