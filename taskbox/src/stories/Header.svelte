<script>
    import Button from './Button.svelte';
    import {page_logo} from "./assets/Layout_data.json";

    export let title = "Page Title";
    export let buttons;

    const openUrl = url => () => {
        window.open(url, '_blank');
    }
</script>

<header>
    <div class="container">
        <div class="wrapper">
            <h1 class="title">{title}</h1>
            <div class="button-container">
                {#each buttons as {label, url}, index}
                    <Button class="button" action={openUrl(url)} label={label}/>
                {/each}
            </div>
        </div>
        <img class="logo" src={page_logo} alt="pageLogo">
    </div>
</header>

<style>
    @font-face {
        font-family: mainThemeFont;
        src: url("./assets/font/The Foregen Rough One.ttf");
    }

    h1 {
        font-family: mainThemeFont, serif;
        color: var(--label-text);
        margin: 0;
        font-size: 40px;
    }

    .wrapper {
        padding: 0.5em;
        height: min-content;
        display: flex;
        align-items: center;
        flex-wrap: revert;
        justify-content: space-between;
        background-color: var(--section-bg);
    }


    .logo {
        width: 100%;
        margin: 0 auto;
    }

    @media screen and (max-width: 600px) {
        .logo {
            display: none;
        }

        .button-container {
            display: flex;
            flex-wrap: wrap-reverse;
            flex-direction: row-reverse;
        }
    }

    @media screen and (min-width: 600px) {
        .button-container {
            display: flex;
        }
    }
</style>
