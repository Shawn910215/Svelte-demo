<!-- Footer.svelte -->
<script>
 export let numItems = 0;
 export let numPacked = 0;
 export let percentage = 0;
</script>

<footer class="stats">
 {#if numItems === 0}
   <em>Start adding some items to your packing list</em>
 {:else}
   <em>
     {#if percentage === 100}
       You got everything! Ready to go✈️
     {:else}
       You have {numItems} items on your list, and you already packed {numPacked} ({percentage}%)
     {/if}
   </em>
 {/if}
</footer>
