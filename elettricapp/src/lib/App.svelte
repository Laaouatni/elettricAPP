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
        value: 48,
      },
      {
        isResistenza: true,
        value: 120,
      },
      [
        {
          isResistenza: true,
          value: 1200,
        },
        {
          isResistenza: true,
          value: 800,
        },
        {
          isResistenza: true,
          value: 56,
        },
      ],
    ],
    options: {
      isSerie: false,
    },
  };
</script>

<NavbarOptions bind:arrayList />

<ListData bind:arrayList />
<Calcoli bind:arrayList/>

<!-- <NavbarPagesBottom /> -->
