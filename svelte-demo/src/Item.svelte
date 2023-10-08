<!-- Item.svelte -->
<script>
 export let item;
 export let handleToggleItem;
 export let handleDeleteItem;
</script>

<li>
 <input
   type="checkbox"
   bind:checked={item.packed}
   on:change={() => handleToggleItem(item.id)}
 />
 <span style:crossed={item.packed}>
   {item.quantity} {item.description}
 </span>
 <button on:click={() => handleDeleteItem(item.id)}>❌</button>
</li>
