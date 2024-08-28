<script lang="ts">
    // export let name;
    let firstName = "Jimi";
    let lastName = "Hendrix";
    let beltColor = "black";

    // ractive value
    $: fullName = `${firstName} ${lastName}`;

    // reactive statement
    $: console.log(beltColor);

    // data for the loop
    interface Nakamma {
        name: String;
        role: String;
        id: Number;
    }

    let crewMembers: Nakamma[] = [
        { name: "Luffy", role: "captain", id: 1 },
        { name: "Zoro", role: "swordsman", id: 2 },
        { name: "Nami", role: "navigator", id: 3 },
    ];
</script>

<main>
    <p style="color: {beltColor};">{fullName} - {beltColor}</p>
    <div class="input-container">
        <input type="text" bind:value={firstName} />
        <input type="text" bind:value={lastName} />
        <input type="text" bind:value={beltColor} />
    </div>

    <!-- Loop exemple -->
    <section>
        <h3>Strawhat crew nakama's</h3>
        <article class="card-container">
            {#each crewMembers as nakama (nakama.id) }
                <div class="card">
                    <h4>{nakama.name}</h4>
                    <p>{nakama.role} of the crew !</p>
                </div>
                {:else}
                <p>There ar no nakama to display...</p>
            {/each}
        </article>
    </section>
</main>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
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

    .card-container {
        display: flex;
        justify-content: space-around;
        margin: auto;
        max-width: 80%;
        flex-wrap: wrap;
    }

    .card {
        background: rgba(240, 128, 128, 0.3);
        flex: 1;
        padding: 1rem;
        margin: 0 2rem;
        border-radius: 0.5rem;
        box-shadow: 0.25rem 0.25rem 0.25rem rgba(211, 211, 211, 0.9);
        &:hover {
            box-shadow: 0.5rem 0.5rem 0.5rem rgba(211, 211, 211, 0.9);
        }
    }
</style>
