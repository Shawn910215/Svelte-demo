<script>
  let newItem = '';
  let items = [];

  function addItem() {
    if (newItem.trim() !== '') {
      items = [...items, newItem];
      newItem = '';
    }
  }
</script>
<main>
<h1>Svelte Demo App</h1>

<input bind:value={newItem} placeholder="Enter an item..." />

<button on:click={addItem}>Add</button>

<ul>
  {#each items as item (item)}
    <li>{item}</li>
  {/each}
</ul>
</main>


<style>
  h1 {
    text-align: center;
    margin-bottom: 20px;
    color: #333;
  }

  input {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
  }

  button {
    display: block;
    width: 100%;
    padding: 10px;
    background-color: #007acc;
    color: #fff;
    border: none;
    cursor: pointer;
  }

  button:hover {
    background-color: #005ea6;
  }

  ul {
    list-style: none;
    padding: 0;
  }

  li {
    background-color: #f2f2f2;
    padding: 10px;
    margin-bottom: 5px;
    border-radius: 5px;
  }
</style>