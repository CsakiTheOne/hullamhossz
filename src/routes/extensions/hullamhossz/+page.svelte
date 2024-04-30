<script>
    import Button from "$lib/components/Button.svelte";
    import Card from "$lib/components/Card.svelte";
    import ConnectionBar from "$lib/components/ConnectionBar.svelte";

    let wavelengthLeft = 0;
    let wavelengthRight = 0;
    let sympathyLeft = 0;
    let sympathyRight = 0;
    $: wavelengthMax = Math.max(wavelengthLeft, wavelengthRight, 1);
    $: wavelengthLeftPercent = (wavelengthLeft / wavelengthMax) * 100;
    $: wavelengthRightPercent = (wavelengthRight / wavelengthMax) * 100;
    $: sympathyLeftPercent = (sympathyLeft / wavelengthMax) * 100;
    $: sympathyRightPercent = (sympathyRight / wavelengthMax) * 100;
</script>

<main class="content-grid" style="row-gap: 16px;">
    <h1><a href="./">hullámhossz</a></h1>

    <Card
        className="content-grid"
        style="background: var(--color-secondary); color: var(--color-on-secondary); row-gap: 16px; padding: 16px 0;"
    >
        <p>
            Mennyire vagytok egy hullámhosszon? Húzzatok lapokat felváltva. Ha
            válaszoltál, nyomj a te oldaladon lévő "+" gombra, majd add át a
            lapot a másiknak. Ha ő is válaszolt, mehet a "+" a másik oldalon is.
        </p>

        <ConnectionBar
            valueLeft={wavelengthLeftPercent}
            valueRight={wavelengthRightPercent}
        />

        <div style="display: flex; justify-content: space-evenly;">
            <div>
                <Button on:click={() => { if (wavelengthLeft > 0) wavelengthLeft--; }}>-</Button>
                <span>{wavelengthLeft}</span>
                <Button on:click={() => { if (wavelengthLeft < 80) wavelengthLeft++; }}>+</Button>
            </div>
            <div>
                <Button on:click={() => { if (wavelengthRight > 0) wavelengthRight--; }}>-</Button>
                <span>{wavelengthRight}</span>
                <Button on:click={() => { if (wavelengthRight < 80) wavelengthRight++; }}>+</Button>
            </div>
        </div>
    </Card>

    <Card
        className="content-grid"
        style="background: var(--color-secondary); color: var(--color-on-secondary); row-gap: 16px; padding: 16px 0;"
    >
        <h3>Szimpátia</h3>
        <p>
            Egyetértesz vagy tetszik a játékos partnered válasza? Nyomj a pluszra itt is!
        </p>

        <ConnectionBar
            valueLeft={sympathyLeftPercent}
            valueRight={sympathyRightPercent}
        />

        <div style="display: flex; justify-content: space-evenly;">
            <div>
                <Button on:click={() => { if (sympathyLeft > 0) sympathyLeft--; }}>-</Button>
                <span>{sympathyLeft}</span>
                <Button on:click={() => { if (sympathyLeft < 80) sympathyLeft++; }}>+</Button>
            </div>
            <div>
                <Button on:click={() => { if (sympathyRight > 0) sympathyRight--; }}>-</Button>
                <span>{sympathyRight}</span>
                <Button on:click={() => { if (sympathyRight < 80) sympathyRight++; }}>+</Button>
            </div>
        </div>
    </Card>
</main>

<style>
    main > * {
        text-align: center;
    }
</style>
