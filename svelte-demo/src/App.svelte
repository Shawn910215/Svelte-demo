
<script>
  import { onMount } from "svelte";
  import Logo from './Logo.svelte';
  import Form from './Form.svelte';
  import PackingList from './PackingList.svelte';
  import Footer from './Footer.svelte';

  let items = [
    { id: 1, description: "Passports", quantity: 2, packed: true },
    { id: 2, description: "Socks", quantity: 12, packed: false },
    { id: 3, description: "Charger", quantity: 1, packed: false },
  ];

  function handleAddItem(description, quantity) {
    const newItem = { id: Date.now(), description, quantity, packed: false };
    items = [...items, newItem];
    calculateStats();
    // description="";
    // quantity=1;
  }

  function handleDeleteItem(id) {
    items = items.filter((item) => item.id !== id);
    calculateStats();
  }

  function handleToggleItem(id) {
    items = items.map((item) =>
    item.id === id ? { ...item, packed: !item.packed } : item
  );
    console.log("sdf")
    // Recalculate the statistics after toggling
    calculateStats();
  }

  let numItems = 0;
  let numPacked = 0;
  let percentage = 0;

  function calculateStats() {
    numItems = items.length;
    numPacked = items.filter((item) => item.packed).length;
    percentage = Math.round((numPacked / numItems) * 100);
  }

  onMount(() => {
    calculateStats();
  });

</script>

<main>
  <Logo />
  <Form {handleAddItem} />
  <PackingList {items} {handleToggleItem} {handleDeleteItem} />
  <Footer {numItems} {numPacked} {percentage} />
</main>
