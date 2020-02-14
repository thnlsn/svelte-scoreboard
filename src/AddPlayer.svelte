<script>
  let player = {
    name: "",
    score: 0
  };
</script>

<form class="grid-3">
  <input type="text" placeholder="Player Name" bind:value={player.name} />
  <input type="text" placeholder="Player Points" bind:value={player.score} />
  <input type="submit" class="btn btn-primary" value="Add Player" />
</form>
