<!-- Form.svelte -->
<script>
 export let description = "";
 export let quantity = 1;
 export let handleAddItem = () => {}; // Define this function in App.svelte
 function addItem(){
  handleAddItem(description,quantity);
  description="";
  quantity=1;
 }
</script>

<form class="add-form" on:submit|preventDefault={() => {}}>
 <h3>What do you need for your 😀 trip</h3>
 <select bind:value={quantity}>
   {#each Array.from({ length: 20 }, (_, i) => i + 1) as num}
     <option value={num}>{num}</option>
   {/each}
 </select>
 <input type="text" bind:value={description} placeholder="Item..." />
 <button on:click={addItem}>Add</button>
</form>
