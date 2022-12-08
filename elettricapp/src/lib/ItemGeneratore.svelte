<script>
  export let item;
  export let index;
</script>

<div
  class="grid grid-cols-[auto_1fr] rounded-md border-2 border-blue-400 text-2xl"
>
  <span class="px-6 bg-blue-400 flex items-center text-white">{index}</span>
  <span class="p-4 flex justify-center">{item.value} Ω</span>
</div>
