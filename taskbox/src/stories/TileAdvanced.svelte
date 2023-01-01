<script>

    import ModalDialog from './ModalDialog.svelte';
    import TileSingle from "./TileSingle.svelte";
    import TileMedia from "./TileMedia.svelte";

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
        <TileMedia media_type="image" src={image}/>
        <TileSingle text={text}/>
<!--        <img src={image} alt="" class="image" on:click="{() => showModal = true}">-->
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
        background-color: var(--section-bg);
        display: flex;
        flex-direction: row;
    }

    .container-reverse {
        background-color: var(--section-bg);
        display: flex;
        flex-direction: row-reverse;
    }

</style>
