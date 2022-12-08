<script>
  export let arrayList;
  export let valueItem;

  function addGenerator() {
    arrayList = [
      ...arrayList,
      {
        isResistenza: false,
        value: valueItem,
      },
    ];
  }
</script>

<button
  class="p-4 bg-blue-500 text-white font-semibold rounded-xl w-full text-2xl"
  on:click={addGenerator}
>
  + Generatore
</button>
