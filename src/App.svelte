<script lang="ts">
  import AddBill from "./components/add-bill.svelte";
</script>

<main>
  <h1>Bills reminder</h1>
  <AddBill />
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }
</style>
