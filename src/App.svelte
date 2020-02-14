<script>
  let name = "John Doe"; //export IF it is passed in by another file
  let points = 100;

  const addPoint = () => (points += 1); //being passed into the button on:click
  const removePoint = () => (points -= 1); //being passed into the button on:click
</script>

<style>
  h1 {
    color: #204f6e;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>

  <div class="container">
    <div class="card">
      <h1>{name}</h1>
      <h3>{points}</h3>
      <button class="btn" on:click={addPoint}>+1</button>
      <button class="btn btn-dark" on:click={removePoint}>+1</button>
      <input type="number" bind:value={points} />
    </div>
  </div>

</main>
