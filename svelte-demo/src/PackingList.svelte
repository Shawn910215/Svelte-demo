<!-- PackingList.svelte -->
<script>
 import Item from './Item.svelte';
 export let items;
 export let handleToggleItem;
 export let handleDeleteItem;
</script>

<div class="list">
 <ul>
   {#each items as item (item.id)}
     <Item {item} {handleToggleItem} {handleDeleteItem} />
   {/each}
 </ul>
</div>
