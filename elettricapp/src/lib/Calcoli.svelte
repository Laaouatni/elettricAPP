<script>
  import CalcoloCorrenteTotale from "./CalcoloCorrenteTotale.svelte";
  import CalcoloRp from "./CalcoloRp.svelte";
  import CalcoloRt from "./CalcoloRt.svelte";

  export let arrayList;
  let Rt;
</script>

<div class="grid gap-4 p-4">
  <h1 class="text-3xl font-bold">Calcoli.</h1>

  <CalcoloRp {arrayList} />
  <CalcoloRt {arrayList} bind:Rt />
  <CalcoloCorrenteTotale {arrayList} bind:Rt />
</div>
