<script>
    import {createEventDispatcher, onDestroy} from 'svelte';
    import Button from "./Button.svelte";

    export let type;
    let modal;
    export let close_callback

    const handle_keydown = e => {
        if (e.key === 'Escape') {
            close_callback();
            return;
        }

        if (e.key === 'Tab') {
            // trap focus
            const nodes = modal.querySelectorAll('*');
            const tabbable = Array.from(nodes).filter(n => n.tabIndex >= 0);

            let index = tabbable.indexOf(document.activeElement);
            if (index === -1 && e.shiftKey) index = 0;

            index += tabbable.length + (e.shiftKey ? -1 : 1);
            index %= tabbable.length;

            tabbable[index].focus();
            e.preventDefault();
        }
    };

    const previously_focused = typeof document !== 'undefined' && document.activeElement;

    if (previously_focused) {
        onDestroy(() => {
            previously_focused.focus();
        });
    }
</script>

<svelte:window on:keydown={handle_keydown}/>


<div class="background modal-background-logoff" on:click={close_callback} on:keydown={close_callback}></div>
<div class="modal" role="dialog" aria-modal="true" bind:this={modal}>
    <img class="img" src="assets/images/coffee.png" alt="logo">
    <div>
        <div class="dialog_title">Odhlásit se</div>
        <div class="dialog_text">Dejte si kafe a odpočiňte si :-)</div>
    </div>
    <Button toggleView={close_callback} bottomTopMargin="24" label="Odhlasit se" color="#84B2C2"/>
</div>

<style>

    .dialog_title {
        font-family: 'Roboto', sans-serif;
        font-style: normal;
        font-weight: 700;
        font-size: 40px;
        line-height: 48px;
    }

    .dialog_text {
        font-family: 'Roboto', sans-serif;
        font-style: normal;
        font-weight: 500;
        font-size: 20px;
        line-height: 28px;
        align-items: center;
    }

    .img {
        margin-top: 32px;
        height: 160px;
        width: 160px;
    }

    .background {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        backdrop-filter: blur(6px);
    }

    .modal-background-logoff {
        background: rgba(166, 226, 245, 0.8);

    }

    .modal-background-stop {
        background: rgba(218, 74, 84, 0.8);
    }

    .modal {
        text-align: center;
        position: absolute;

        padding: 24px;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);

        min-width: 440px;
        min-height: 560px;
        height: calc(100vh - 464px);
        width: calc(100vw - 160px);

        border-radius: 8px;
        background: white;
    }

</style>