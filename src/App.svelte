<script>
    export let name;
    let beltColor = "black";

    // handle to change color
    const hanldeClick = () => {
        beltColor = "green";
    };

    // const handleInput = (event) => {
    //     beltColor = event.target.value;
    // };
</script>

<main>
    <h1>Hello {name}!</h1>
    <p>{beltColor} belt level ?</p>
    <div class="select-color-container">
        <!-- <input
        type="text"
        name="chooseBeltColor"
        id="chooseBeltColor"
        value={beltColor}
        on:input={handleInput}
        /> -->
        <!-- Shorter way to create tow way data binding -->
        <input
            type="text"
            name="chooseBeltColor"
            id="chooseBeltColor"
            bind:value={beltColor}
        />
        <button
            on:click={hanldeClick}
            style="background: {beltColor};"
        >
            Update belt color
        </button>
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

    .select-color-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    button {
        color: #fff;
        border: none;
        border-radius: 0.5rem;
        padding: 0.5rem;
    }
</style>
