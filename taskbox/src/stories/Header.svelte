<script>
    import Button from './Button.svelte';
    import font from './assets/font/The Foregen Rough One.ttf'
    export let title = "Industrial Engineer";

    function download() {
        alert("download")
    }
</script>

<header>
    <div class="container">
        <h1 class="title">{title}</h1>
        <div>
            <Button action={download} label="Download"/>
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


    .container {
        padding: 0.5em;
        height: min-content;
        display: flex;
        align-items: center;
        justify-content: space-between;
        background-color: var(--section-bg);
    }
</style>
