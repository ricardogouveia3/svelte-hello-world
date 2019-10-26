<script>
  import Greeting from "./Greeting.svelte";

  export let name;
</script>

<style>
  h1 {
    color: purple;
  }

  h2 {
    color: purple;
    font-family: "Comic Sans MS";
    font-size: 2em;
  }
</style>

<Greeting firstName="Svelte" lastName="Dev" />
