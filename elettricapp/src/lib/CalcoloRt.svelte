<script>
  export let arrayList;

  $: allSerie = arrayList.data
    .filter(
      (item) => !Array.isArray(item) && item.isResistenza,
    )
    .map((item) => item.value)
    .reduce(
      (thisValue, total) =>
        parseFloat(thisValue) + parseFloat(total),
    );

  $: allParallelo = arrayList.options.RpValues.reduce(
    (thisValue, total) => {
      return parseFloat(thisValue) + parseFloat(total);
    },
  );

  $: calculateRt = allSerie + allParallelo;

  export let Rt = calculateRt
</script>

<div>
  <div class="flex flex-wrap gap-4 border p-4">
    <div class="flex place-items-center gap-2">
      <span class="font-bold">Rt</span> =
    </div>
    <div>
      {#each arrayList.data as itemSerie, indexSerie}
        {#if !Array.isArray(itemSerie) && itemSerie.isResistenza}
          <span>{itemSerie.value}</span>
          {#if indexSerie !== arrayList.data.length}
            +
          {/if}
        {/if}
      {/each}

      {#each arrayList.options.RpValues as RpItem, indexRp}
        <span>{RpItem}</span>

        {#if indexRp !== arrayList.options.RpValues.length - 1}
          +
        {:else}
          =
        {/if}
      {/each}
    </div>

    <div>{calculateRt} Ω</div>
  </div>
</div>
