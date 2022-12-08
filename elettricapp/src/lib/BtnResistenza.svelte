<script>
  export let arrayList;
  export let valueItem;

  function addResistor() {
    arrayList = [
      ...arrayList,
      {
        isResistenza: true,
        value: valueItem,
      },
    ];
  }
</script>

<button
  class="p-4 bg-cyan-500 text-white font-semibold rounded-xl w-full text-2xl"
  on:click={addResistor}
>
  + Resistenza
</button>
