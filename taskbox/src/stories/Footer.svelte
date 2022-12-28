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

    .container {
        margin-top: 10px;
        height: 50px;
        display: grid;
        grid-template-columns: 1fr 1fr;
        background-color: #dddddd;
    }


    .footer-left {
        text-align: left;
        color: #1ea7fd;
        align-self: center;
    }

    .footer-right {
        text-align: right;
        color: #1ea7fd;
        align-self: center;
    }
</style>