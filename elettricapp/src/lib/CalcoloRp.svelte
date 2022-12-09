<script>
  export let arrayList;

  const PRECISION_FLOAT = 6;

  $: arrayOfParalleli = arrayList.data.filter((item) => {
    return Array.isArray(item);
  });

  function valoriDivisoSotto(itemParallelo) {
    return itemParallelo.map((item) => {
      return (1 / item.value).toFixed(PRECISION_FLOAT);
    });
  }

  function addizioneValoriSotto(itemParallelo) {
    return valoriDivisoSotto(itemParallelo).reduce(
      (thisValue, total) => {
        return parseFloat(thisValue) + parseFloat(total);
      },
    );
  }

  function Rp(itemParallelo) {
    return 1 / addizioneValoriSotto(itemParallelo);
  }
</script>

<div class="grid gap-4 p-4 pb-52">
  <h1 class="text-3xl font-bold">Calcoli.</h1>

  {#each arrayOfParalleli as itemParallelo, indexParallelo}
    <div class="flex flex-wrap gap-4 border p-4">
      <div class="flex place-items-center gap-2">
        <span class="font-bold">Rp{indexParallelo + 1}</span> =
      </div>

      <div class="grid gap-1">
        <div class="text-center">1</div>
        <hr />

        <div class="flex gap-2 text-center">
          {#each valoriDivisoSotto(itemParallelo) as valore, index}
            <div>
              <span>1</span>
              <hr />
              <div>{valore}</div>
            </div>

            <div class="grid place-items-center">
              {#if index !== valoriDivisoSotto(itemParallelo).length - 1}
                +
              {/if}
            </div>
          {/each}
        </div>
      </div>

      <div class="flex gap-4">
        <span class="grid place-items-center">=</span>

        <div class="text-center grid">
          <span>1</span>
          <hr />
          <div>
            {addizioneValoriSotto(itemParallelo)}
          </div>
        </div>
      </div>

      <div class="flex gap-4">
        <span class="grid place-items-center">=</span>

        <div class="text-center grid place-items-center">
          {Rp(itemParallelo).toFixed(PRECISION_FLOAT)} Ω
        </div>
      </div>
    </div>
  {/each}
</div>