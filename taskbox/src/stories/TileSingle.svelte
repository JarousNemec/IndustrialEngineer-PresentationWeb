<script>
    export let text;
</script>

<tilesingle>
    <div class="container">
        <div class="content">
            {text}
        </div>
    </div>
</tilesingle>


<style>
    .container {
        background-color: var(--section-bg);
        padding: 10px;
    }

    .content {
        padding: 10px;
        background-color: var(--section-text);
        border-radius: 5px;
    }
</style>
