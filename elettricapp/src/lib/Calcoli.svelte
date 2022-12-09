<script>
  export let arrayList;

  $: arrayOfParalleli = arrayList.data.filter((item) => {
    return Array.isArray(item);
  });

  function test() {
    let valoriSotto = arrayOfParalleli.map(
      (itemParallelo) => {
        return itemParallelo
          .map((item) => {
            return 1 / item.value;
          })
          .reduce((thisValue, total) => {
            return (
              parseFloat(thisValue) + parseFloat(total)
            );
          });
      },
    );

    return valoriSotto;
  }
</script>

<div class="grid gap-4 p-4 pb-52">
  <h1 class="text-3xl font-bold">Calcoli.</h1>

  <div>Rp = {test()}</div>
</div>
