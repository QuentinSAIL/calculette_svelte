<script>
    export let label;
    export let onClick;
</script>

<button on:click={onClick}>{label}</button>

<style>
    button {
        width: 50px;
        height: 50px;
        font-size: 20px;
        margin: 2px;
    }
</style>