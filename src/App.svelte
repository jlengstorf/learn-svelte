<script>
  import { onDestroy } from "svelte";
  import { count } from "./stores.js";
  import Button from "./Button.svelte";
  import Resetter from "./Resetter.svelte";
  export let name;

  const increment = () => {
    $count += 1;
  };
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1>Hi {name}! {$count}</h1>
  <p>
    Visit the
    <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
    to learn how to build Svelte apps.
  </p>
  <form>
    <input type="text" bind:value={name} />
  </form>
  <Button count={$count} handleClick={increment} />
  <Resetter />
</main>
