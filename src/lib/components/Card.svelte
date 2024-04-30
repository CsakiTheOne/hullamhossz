<script>
    export let style = "";
    export let className = "";
</script>

<div {style} class={className}>
    <slot />
</div>

<style>
    div {
        background: var(--color-primary);
        color: var(--color-on-primary);
        border-radius: 16px;
    }
</style>