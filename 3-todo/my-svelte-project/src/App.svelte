
<!-- JS -->
<script>

    import Navbar from './Navbar.svelte';
    import Crypto from './Crypto.svelte';
    import AddCrypto from './AddCrypto.svelte'

    let cryptos = [
        {
            name: 'EOSIO',
            symbol: 'EOS',
            amount: 1000
        },
        {
            name: 'PAYTOMAT',
            symbol: 'PTI',
            amount: 500
        },
        {
            name: 'EVERIPEDIA',
            symbol: 'IQ',
            amount: 2000
        },
    ]

    const addCrypto = (e) => {
        console.log(e.detail);
        const newCrypto = e.detail;
        cryptos = [...cryptos, newCrypto];
    }

    const deleteCrypto = (e) => {
        console.log('removed');
        cryptos = cryptos.filter(crypto => crypto.name !== e.detail);
    }

</script>

<!-- CSS -->
<style>
    .container {
	    max-width: 800px;
	    margin: auto;
	    overflow: hidden;
	    padding: 0 2rem;
    }

</style>

<!-- HTML -->
<Navbar/>
<div class="container">
    <AddCrypto on:addcrypto = { addCrypto }/>

    {#if cryptos.length === 0} <p>Please add Crytpos</p>
    {:else}
        {#each cryptos as crypto}
        <Crypto name = {crypto.name} 
                symbol = {crypto.symbol} 
                amount = {crypto.amount} 
                on:removecrypto = { deleteCrypto }
                />
        {/each}
    {/if}
</div>


