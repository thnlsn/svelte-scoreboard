<script>
  import { createEventDispatcher } from "svelte";
  import Navbar from "./Navbar.svelte";
  import Player from "./Player.svelte";
  import AddPlayer from "./AddPlayer.svelte";

  let players = [
    {
      name: "Bruce Wayne",
      points: 82
    },
    {
      name: "Clark Kent",
      points: 99
    },
    {
      name: "Diana Prince",
      points: 87
    },
    {
      name: "Barry Allen",
      points: 71
    },
    {
      name: "Arthur Curry",
      points: 58
    },
    {
      name: "Victor Stone",
      points: 70
    },
    {
      name: "John Jones",
      points: 100
    }
  ];

  const addPlayer = e => {
    const newPlayer = e.detail; // detail is what we dispatched in addplayer
    players = [...players, newPlayer]; // players is immutable (like state in react), so we have to spread out a copy and add the new thing to it
  };

  const removePlayer = e => {
    players = players.filter(player => player.name !== e.detail); // return an array without the player with the name in the detail (aka the player clicked)
  };
</script>

<style>
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <Navbar />

  <div class="container">

    <AddPlayer on:addplayer={addPlayer} />

    {#if players.length <= 0}
      <p class="text-center">No Players...</p>
    {:else}
      {#each players as player}
        <Player
          name={player.name}
          points={player.points}
          on:removeplayer={removePlayer} />
      {/each}
    {/if}

  </div>

</main>
