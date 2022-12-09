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
  {#each arrayList.data as itemSerie, indexSerie}
    {#if Array.isArray(itemSerie)}
      <div
        class="border-4 grid grid-cols-[auto_1fr] rounded-lg overflow-hidden"
      >
        <span
          class="px-6 grid items-center text-white text-2xl 
          {itemSerie.isResistenza
            ? 'bg-blue-400'
            : 'bg-cyan-400'}"
        >
          {indexSerie}
        </span>
        <div class="grid gap-4 p-4">
          {#each itemSerie as itemParallelo, indexParallelo}
            <ItemList
              item={itemParallelo}
              index={indexParallelo}
            />
          {/each}
        </div>
      </div>
    {:else}
      <ItemList item={itemSerie} index={indexSerie} />
    {/if}
  {/each}
</div>
