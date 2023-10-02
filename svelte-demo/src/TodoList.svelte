
<script>
  export let items = [];

  function deleteItem(index) {
    items = items.filter((_, i) => i !== index);
  }
</script>

<ul>
  {#each items as item,index (item)}
    <li>
    {item}
    <button on:click={() => deleteItem(index)}>❌</button>
    </li>
  {/each}
</ul>

<style>
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
