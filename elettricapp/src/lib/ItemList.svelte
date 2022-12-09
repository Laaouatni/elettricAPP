<script>
  export let item;
  export let index;
</script>

<div
  class="grid grid-cols-[auto_1fr] rounded-md border-2 text-2xl 
  {item.isResistenza
    ? 'border-cyan-400'
    : 'border-blue-400'}"
>
  <span
    class="px-6 flex items-center text-white 
    {item.isResistenza ? 'bg-cyan-400' : 'bg-blue-400'}"
  >
    {index}
  </span>
  <span class="flex justify-center p-4 gap-2">
    <input
      type="number"
      class="w-full text-center rounded-sm border-trasparent hover:border focus:border-b-2 outline-none
      {item.isResistenza
        ? 'focus:border-b-cyan-400'
        : 'focus:border-b-blue-400'}"
      value={item.value}
    />
    {item.isResistenza ? "Ω" : "V"}
  </span>
</div>
