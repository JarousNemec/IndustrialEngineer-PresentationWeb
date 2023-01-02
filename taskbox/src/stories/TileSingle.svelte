<script>
    export let text;
</script>


<div class="container">
    <div class="content">
        {text}
    </div>
</div>


<style>

    .container {
        background-color: var(--section-bg);
        padding: 10px;
        border-radius: 10px;
    }

    .content {
        padding: 10px;
        background-color: var(--section-text);
        border-radius: 5px;
        font-weight: 500;
        text-align: justify;
        font-family: 'Arial', serif;
        color: var(--content-text);
    }
</style>
