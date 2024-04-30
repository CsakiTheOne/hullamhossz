<script>
    import Card from "$lib/components/Card.svelte";
    import CardTitle from "$lib/components/CardTitle.svelte";
    import Button from "$lib/components/Button.svelte";
    import Footer from "$lib/components/Footer.svelte";
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

    <Footer />
</main>

<style>
    main > * {
        text-align: center;
    }
</style>
