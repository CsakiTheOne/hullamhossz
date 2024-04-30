<script>
    import Card from "$lib/components/Card.svelte";
    import CardTitle from "$lib/components/CardTitle.svelte";
    import Button from "$lib/components/Button.svelte";
</script>

<main class="content-grid" style="row-gap: 16px;">
    <h1><a href="./">hullámhossz</a></h1>

    <h3>
        Kiegészítők a <a href="https://korvonal.com" target="_blank">körvonal</a
        > játékokhoz.
    </h3>

    <Card>
        <div
            style="display: flex; flex-direction: column; gap: 16px; padding: 16px;"
        >
            <CardTitle>hullámhossz</CardTitle>
            <p>
                Szinte mindegyik ketten játszható játékhoz készült kiegészítő.
                Teszteljétek le, hogy mennyire vagytok egy hullámhosszon!
            </p>
            <Button styleInverted on:click={() => window.open("./extensions/hullamhossz")}>Megnyitás</Button>
        </div>
    </Card>

    <div
        class="full-width"
        style="display: flex; flex-direction: column; gap: 16px; padding: 16px; background: var(--color-primary); color: var(--color-on-primary);"
    >
        <p>Made by WholesomeWare</p>
    </div>
</main>

<style>
    main > * {
        text-align: center;
    }
</style>
