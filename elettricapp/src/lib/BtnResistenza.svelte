<script>
  export let arrayList;
  export let valueItem;
  export let isSerie = true;

  function addResistor() {
    const objToAdd = {
      isResistenza: true,
      value: valueItem,
    };

    if (isSerie) {
      arrayList.data = [...arrayList.data, objToAdd];
    } else {
      if (
        !Array.isArray(
          arrayList.data[arrayList.data.length - 1],
        )
      ) {
        arrayList.data = [...arrayList.data, []];
      }

      arrayList.data[arrayList.data.length - 1] = [
        ...arrayList.data[arrayList.data.length - 1],
        objToAdd,
      ];
    }
  }

  $: isSerie == true
    ? (arrayList.options.isSerie = true)
    : (arrayList.options.isSerie = false);
</script>

<div class="flex">
  <div class="flex">
    <button
      class="h-16 w-16 font-semibold text-2xl rounded-tl-lg rounded-bl-lg
      {isSerie
        ? 'bg-teal-300 shadow-lg shadow-teal-400'
        : 'bg-white border-4 border-rose-500 opacity-25'}"
      on:click={() => (isSerie = true)}>S</button
    >
    <button
      class="h-16 w-16 font-semibold text-2xl 
      {isSerie
        ? 'bg-white border-4 border-rose-500 opacity-25'
        : 'bg-teal-300 shadow-lg shadow-teal-400'}"
      on:click={() => (isSerie = false)}>P</button
    >
  </div>
  <button
    class="p-4 bg-cyan-500 text-white font-semibold rounded-tr-lg rounded-br-lg w-full sm:text-2xl text-[3vw]"
    on:click={addResistor}
  >
    +Resistenza
  </button>
</div>
