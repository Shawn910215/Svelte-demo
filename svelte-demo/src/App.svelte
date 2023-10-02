<script>
import TodoList from "./TodoList.svelte";

  let newItem = '';
  let items = [];

  function addItem() {
    if (newItem.trim() !== '') {
      items = [...items, newItem];
      newItem = '';
    }
  }
</script>

<h1>Svelte Todo App</h1>

<input bind:value={newItem} placeholder="Enter an item..." />

<button on:click={addItem}>Add</button>

<TodoList {items} />


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

 
</style>