<script>
    import { createEventDispatcher } from "svelte";

    export let style = "";
    export let styleInverted = false;

    let fullStyle = "";

    if (styleInverted) {
        fullStyle += "background: var(--color-on-primary); color: var(--color-primary);";
    } else {
        fullStyle += "background: var(--color-primary); color: var(--color-on-primary);";
    }

    fullStyle += " " + style;

    const dispatch = createEventDispatcher();
</script>

<button style={fullStyle} on:click={() => dispatch("click")}><slot/></button>

<style>
    button {
        border: none;
        border-radius: 8px;
        padding: 12px 16px;
        cursor: pointer;
        font-weight: bold;
    }
</style>