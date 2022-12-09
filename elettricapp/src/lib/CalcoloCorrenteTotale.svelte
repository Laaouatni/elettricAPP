<script>
  export let arrayList;
  export let Rt;

  let generatoreVolt = arrayList.data.filter(
    (item) => !Array.isArray(item) && !item.isResistenza,
  )[0].value;
</script>

<div class="flex flex-wrap gap-4 border p-4">
  <div class="flex place-items-center gap-2">
    <span class="font-bold">Itot</span> =
  </div>

  <div class="text-center grid">
    <span>{generatoreVolt}</span>
    <hr />
    <div>{Rt}</div>
  </div>

  <div class="grid place-items-center grid-flow-col gap-3">
    <span>=</span>
    <span>{generatoreVolt / Rt} A</span>
  </div>
</div>
