<script>
  import Navbar from "./Navbar.svelte";
  import Player from "./Player.svelte";

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
    }
  ];
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

    {#if players.length <= 0}
      <p>No Players</p>
    {:else}
      {#each players as player}
        <Player name={player.name} points={player.points} />
      {/each}
    {/if}

  </div>

</main>
