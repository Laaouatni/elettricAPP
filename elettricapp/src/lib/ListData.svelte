<script>
  import BtnResistenza from "$lib/BtnResistenza.svelte";
  import BtnGeneratore from "./BtnGeneratore.svelte";
  import ItemGeneratore from "./ItemGeneratore.svelte";
  import ItemResistenza from "./ItemResistenza.svelte";

  let arrayList = generateArray();

  function generateArray(n = 10) {
    let result = [];

    for (let i = 0; i < n; i++) {
      result.push({
        isResistenza: Math.random() > 0.5,
        value: Math.floor(Math.random() * 100),
      });
    }

    return result;
  }
</script>

<div class="sticky top-0 bg-white shadow-lg">
  <div class="p-4 flex gap-4">
    <BtnResistenza />
    <BtnGeneratore />
  </div>
  
  <hr />
</div>

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
