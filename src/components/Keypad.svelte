<script>
    export let label;
    export let onClick;
    export let btnClass = "";
</script>

<button on:click={onClick} class={btnClass}>
    {label}
</button>

<style>
    button {
        width: 50px;
        height: 50px;
        font-size: 20px;
        border-radius: 50%;
        border: none;
        font-weight: bold;
        background-color: #555;
        color: white;
    }

    .orange {
        background-color: #ff9501;
        color: black;
    }

    .grey {
        background-color: #808080;
        color: black;
    }

    .long {
        grid-column: span 2;
        border-radius: 25px;
        width: auto;
    }

    .very-long {
        grid-column: span 3;
        border-radius: 25px;
        width: auto;
    }
</style>