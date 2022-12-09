<script>
  import Calcoli from "./Calcoli.svelte";
  import ListData from "./ListData.svelte";
  import NavbarOptions from "./NavbarOptions.svelte";
  import NavbarPagesBottom from "./NavbarPagesBottom.svelte";

  // let arrayList = {
  //   data: [
  //     {
  //       isResistenza: false,
  //       value: 100,
  //     },
  //   ],
  //   options: {},
  // };

  let arrayList = {
    data: [
      {
        isResistenza: false,
        value: 50,
      },
    ],
    options: {
      isSerie: false,
      RpValues: [],
    },
  };
</script>

<NavbarOptions bind:arrayList />

<ListData bind:arrayList />
<Calcoli bind:arrayList />

<!-- <NavbarPagesBottom /> -->
