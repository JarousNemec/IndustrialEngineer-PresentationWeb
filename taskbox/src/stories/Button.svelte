<script>
    export let label = '';
    export let action = () =>{
        alert("default action")
    }
</script>

<div class="container" on:click={action}>  {label}</div>

<style>
.container{
    background-color: var(--button);

    padding: 0.5em 0.9em;
    color: var(--content-text);
    cursor: pointer;
    border-color: var(--section-bg);

    border-width: 2px;
    border-radius: 10px;
    border-style: solid;

    font-family: sans-serif;
    font-size: 14px;
}
</style>

