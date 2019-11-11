<script>

import { createEventDispatcher } from 'svelte';

const dispatch = createEventDispatcher();
const onSubmit = (e) => {
    e.preventDefault();
    dispatch("addcrypto", crypto)
    crypto = {
        name:"",
        symbol:"",
        amount:0
    }
}

  let crypto = {
    name: "",
    symbol: "",
    amount: 0
  };
</script>

<style>
  /* Forms */
  input {
    margin: 1.2rem 0;
  }

  .form-text {
    display: block;
    margin-top: 0.3rem;
    color: #888;
  }

  input[type="text"],
  input[type="email"],
  input[type="password"],
  input[type="date"],
  input[type="number"],
  select,
  textarea {
    display: block;
    width: 100% !important;
    padding: 0.4rem;
    font-size: inherit;
    border: 1px solid #ccc;
  }

  input[type="submit"],
  button {
    font: inherit;
  }

  .form-group {
    margin: 1.2rem 0;
  }

  .form-group input {
    margin: 0.2rem 0;
  }

  .form-container {
    max-width: 500px;
    margin: 2rem auto;
    overflow: hidden;
    padding: 0 2rem;
  }
</style>

<form class="form-group" on:submit = { onSubmit }>
  <input type="text" placeholder="crypto" bind:value={crypto.name} />
  <input type="text" placeholder="symbol" bind:value={crypto.symbol} />
  <input type="number" placeholder="amount" bind:value={crypto.amount} />
  <input type="submit" value="Add Crypto" />
</form>
