<script>
    // export let name;
    let firstName = "Jimi";
    let lastName = "Hendrix";
    let beltColor = "black";

    // ractive value
    $: fullName = `${firstName} ${lastName}`;

    // reactive statement
    $: console.log(beltColor);
</script>

<main>
    <p style="color: {beltColor};">{fullName} - {beltColor}</p>
    <div class="input-container">
        <input type="text" bind:value={firstName} />
        <input type="text" bind:value={lastName} />
        <input type="text" bind:value={beltColor} />
    </div>
</main>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }

    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }

    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }

    .input-container {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>
