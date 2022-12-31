<script>
    import Button from './Button.svelte';

    export let title = "Industrial Engineer";

    function download() {
        alert("downloadsss")
    }
</script>

<header>
    <div class="container">
        <div class="wrapper">
            <h1 class="title">{title}</h1>
            <div>
                <Button class="button" action={download} label="Download"/>
            </div>
        </div>
        <div>
            <img class="logo" src="assets/images/pagelogo.png" alt="pageLogo">
        </div>
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

    .container {

    }

    .logo {
        max-width: 100%;
        margin: 0 auto;
    }

    @media screen and (max-width: 600px) {
        .logo{
            display: none;
        }
    }
</style>
