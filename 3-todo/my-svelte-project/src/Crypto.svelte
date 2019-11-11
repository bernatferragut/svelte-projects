
<!-- JS -->
<script>

    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    import Navbar from './Navbar.svelte'

    export let name;
    export let symbol;
    export let amount;
    let showControls = false;

    const addToken = ()=> amount+=1;
    const removeToken = ()=> amount-=1;
    const toggleControls = ()=> showControls =! showControls;

    const deleteCrypto = () => {
        dispatch("removecrypto", name)
    }

</script>

<!-- CSS -->
<style >
    .symbol {
        font-size: 1.5rem;
        color: lightgray;
    }

    h1 {
        letter-spacing: 8px
    }

    h3 {
        color: lightgray;
    }

    .container {
	    max-width: 800px;
	    margin: auto;
	    overflow: hidden;
	    padding: 0 2rem;
    }

    .card {
	    padding: 1rem;
	    border: #ccc 1px dotted;
	    margin: 0.7rem 0;
    }

    .btn-light {
        width: 20%;
        border-radius: 4px;
        color: black;
        background-color: white;
    }

    .btn-dark {
        width: 20%;
        border-radius: 4px;
        border-style: solid black;
        border-width: 1px;
        border-color: black;
        color:white;
        background-color: black;
    }

    .btn-small {
        margin: 10px 10px;

        font-size: 10px;
        width: 20px;
        border-radius: 4px;
        border-style: solid;
        border-width: 1px;
        border-color: lightgray;
        color:black;
        background-color: white;
    }

    input {
        width : 50%;
    }


</style>

<!-- HTML -->

<div class="card">
    <h2>{ name } | <span class="symbol">{ symbol }</span>
        <button on:click = {toggleControls} class="btn-small">{#if showControls} - { :else } + { /if }</button>
        <button class="btn-small" on:click = { deleteCrypto }> - </button>
    </h2>
    {#if showControls}
        <button class="btn-light" on:click={addToken}> + </button>
        <button class="btn-dark" on:click={removeToken}> - </button>
    {:else}
        <h3> No Controls </h3>
    {/if}

    <h1>{ amount }</h1>

    <input type="number" bind:value = { amount }>
</div>


