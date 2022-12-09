<script>
  import ListData from "./ListData.svelte";
  import NavbarOptions from "./NavbarOptions.svelte";

  let arrayList = {
    data: [
      {
        isResistenza: false,
        value: 100,
      },
    ],
    options: {},
  };
</script>

<NavbarOptions bind:arrayList />

<ListData bind:arrayList />
