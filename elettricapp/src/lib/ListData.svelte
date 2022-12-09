<script>
  // import ItemGeneratore from "./ItemGeneratore.svelte";
  // import ItemResistenza from "./ItemResistenza.svelte";
  import ItemList from "./ItemList.svelte";
  import NavbarOptions from "./NavbarOptions.svelte";

  let arrayList = { data: [], options: {} };

  $: console.log(arrayList);
</script>

<NavbarOptions bind:arrayList />

<div class="grid gap-4 p-4">
  <h1 class="text-3xl font-bold">Lista.</h1>
  {#each arrayList.data as item, index}
    <ItemList {item} {index} />
  {/each}
</div>
