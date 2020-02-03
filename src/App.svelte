<script>
  import Router from "svelte-spa-router";
  import Home from "./pages/Home.svelte";
  import Add from "./pages/Add.svelte";
  import Edit from "./pages/Edit.svelte";

  const routes = {
    "/": Home,
    "/add": Add,
    "/edit/:id": Edit,
    "*": Home
  };
</script>

<style>
  main {
    background-color: rgb(255, 251, 246);
    padding: 2em;
    width: 100%;
    height: 100%;
    overflow-y: auto;
  }
</style>

<main>
  <Router {routes} />
</main>
