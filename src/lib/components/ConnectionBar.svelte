<script>
    export let valueLeft = 0;
    export let valueRight = 0;
</script>

<div class="progress-bar">
    <div class="progress-bar-fill" style="width: {valueLeft / 2}%"></div>
    <div class="progress-bar-fill progress-bar-fill-right" style="width: {valueRight / 2}%"></div>
</div>

<style>
    .progress-bar {
        position: relative;
        min-width: 100px;
        height: 24px;
        background-color: var(--color-surface);
        border-radius: 16px;
        overflow: hidden;
        border: var(--color-background) 4px solid;
        outline: var(--color-primary) 4px solid;
    }

    .progress-bar-fill {
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        background-color: var(--color-primary);
        transition: width .3s ease-in-out;
    }

    .progress-bar-fill-right {
        right: 0;
        left: auto;
    }
</style>
