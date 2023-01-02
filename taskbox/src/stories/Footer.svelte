<script>
    export let text_left;
    export let text_right;

</script>

<footer>
    <div class="container">
        <div class="footer-left">{text_left}</div>
        <div class="footer-right">{text_right}</div>
    </div>
</footer>

<style>
    @font-face {
        font-family: mainThemeFont;
        src: url("./assets/font/The Foregen Rough One.ttf");
    }

    .container {
        display: flex;
        flex-wrap: wrap;
        background-color: var(--section-bg);
        padding: 1em;
        font-family: mainThemeFont, serif;
    }


    .footer-left {
        text-align: left;
        color: white;
        align-self: center;
        margin: 0 auto 0 0;
    }

    .footer-right {
        text-align: right;
        color: white;
        align-self: center;
        margin: 0 0 0 auto;
    }
</style>