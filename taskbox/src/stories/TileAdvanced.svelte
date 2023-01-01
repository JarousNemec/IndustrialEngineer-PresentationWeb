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


<div>
    <div class={even ? "container" :"container-reverse"}>
        <TileMedia media_type="image" src={image}/>
        <TileSingle text={text}/>
    </div>

    {#if showModal}
        <ModalDialog close_callback={close} on:close="{() => showModal = false}"/>
    {/if}

</div>

<style>

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
