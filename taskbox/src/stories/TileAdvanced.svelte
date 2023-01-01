<script>

    import ModalDialog from './Modal.svelte';
    import Modal, {getModal} from './Modal.svelte'
    import TileSingle from "./TileSingle.svelte";
    import TileMedia from "./TileMedia.svelte";

    let showModal = false;

    export let image;
    export let text;
    export let even;

    function close() {
        showModal = false
    }


    let name = 'world';

    let selection

    // Callback function provided to the `open` function, it receives the value given to the `close` function call, or `undefined` if the Modal was closed with escape or clicking the X, etc.
    function setSelection(res) {
        selection = res
    }

</script>


<div>
    <div class={even ? "container" :"container-reverse"}>
        <TileMedia media_type="image" src={image}/>
        <TileSingle text={text}/>
        <button on:click={()=>getModal().open()}>
            Open First Popup
        </button>
    </div>

    {#if showModal}
        <ModalDialog close_callback={close} on:close="{() => showModal = false}"/>
    {/if}

    <Modal>
        <h1>Hello {name}!</h1>
    </Modal>

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
