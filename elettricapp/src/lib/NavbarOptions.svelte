<script>
  import BtnResistenza from "$lib/BtnResistenza.svelte";
  import BtnGeneratore from "./BtnGeneratore.svelte";

  export let arrayList;
  let valueItem = 100;
</script>

<div class="sticky top-0 bg-white shadow-lg p-4 grid gap-4">
  <div>
    <input
      class="border-2 w-full p-3 text-3xl rounded-md"
      min="0"
      bind:value={valueItem}
      type="number"
      placeholder="enter value"
    />
  </div>
  <div class="flex gap-4">
    <BtnResistenza bind:arrayList bind:valueItem />
    <BtnGeneratore bind:arrayList bind:valueItem />
  </div>
</div>
