<script>
  import ItemGeneratore from "./ItemGeneratore.svelte";
  import ItemResistenza from "./ItemResistenza.svelte";
  import NavbarOptions from "./NavbarOptions.svelte";

  let arrayList = [];
</script>

<NavbarOptions bind:arrayList />

<div class="grid gap-4 p-4">
  <h1 class="text-3xl font-bold">Lista.</h1>
  {#each arrayList as item, index}
    {#if item.isResistenza}
      <ItemResistenza {item} {index} />
    {:else}
      <ItemGeneratore {item} {index} />
    {/if}
  {/each}
</div>
