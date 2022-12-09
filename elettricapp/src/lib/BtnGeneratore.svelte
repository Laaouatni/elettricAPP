<script>
  export let arrayList;
  export let valueItem;

  function addGenerator() {
    arrayList.data = [
      ...arrayList.data,
      {
        isResistenza: false,
        value: valueItem,
      },
    ];
  }
</script>

<button
  class="p-4 px-6 bg-blue-500 text-white font-semibold rounded-xl w-full sm:text-2xl text-[3vw]"
  on:click={addGenerator}
>
  +Generatore
</button>
