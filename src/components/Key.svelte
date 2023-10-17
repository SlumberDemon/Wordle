<script>
    export let char;
    export let keyPress;
    const keyClass = char == "ENTER" || char == "DEL" ? "key special" : "key";
</script>

<div class={keyClass} on:click={() => keyPress(char.toUpperCase())}>
    {char.toUpperCase()}
</div>

<style>
    .key {
        background-color: var(--bg);
        color: white;
        padding: 20px 18px;
        margin: 4px 3px;
        cursor: pointer;
        border-radius: 4px;
        transition: background-color 0.3s;
    }

    .key:hover {
        background-color: var(--orange);
    }

    .special {
        padding: 20px 35px;
    }
</style>
