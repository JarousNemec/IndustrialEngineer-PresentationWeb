<script>

        import ModalDialog from './ModalDialog.svelte';

        let showModal = false;

        export let image;
        export let text;

        function close() {
                showModal = false
        }

</script>


<tile >
        tile - {image} {text}
        <button on:click="{() => showModal = true}">
                show modal
        </button>

        {#if showModal}
                <ModalDialog close_callback={close} on:close="{() => showModal = false}"/>
        {/if}

</tile>

