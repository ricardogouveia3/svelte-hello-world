<script>
  export let firstName;
  export let lastName;

  $: name = firstName + " " + lastName;

  let user = { loggedIn: false };
  function toggleLogin() {
    user.loggedIn = !user.loggedIn;
  }

  let frameworks = [
    { id: 1, name: "Svelte" },
    { id: 2, name: "Angular" },
    { id: 3, name: "React" },
    { id: 4, name: "Vue" }
  ];

  let m = { x: 0, y: 0 };
  function handleMousemove(event) {
    m.x = event.clientX;
    m.y = event.clientY;
  }
</script>

<style>
  h2 {
    color: purple;
    font-family: "Comic Sans MS";
    font-size: 2em;
  }
  li {
    list-style-type: none;
    text-indent: 0;
  }
  div {
    width: 300px;
    height: 300px;
    color: purple;
    background: lightseagreen;
  }
</style>

<label for="name">Nome:</label>
<input bind:value={name} type="text" id="name">
<h2>Hello {name}</h2>

{#if user.loggedIn}
  <span>User is logged!</span>
  <button on:click={toggleLogin}>Logout</button>
{:else}
  <span>No user logged!</span>
  <button on:click={toggleLogin}>Login</button>
{/if}

<h2>List of frameworks</h2>
<ul>
  {#each frameworks as { id, name }}
    <li>{id}: {name}</li>
  {/each}
</ul>

<div on:mousemove={handleMousemove}>The mouse position is {m.x} x {m.y}</div>
