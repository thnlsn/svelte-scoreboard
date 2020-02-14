<script>
  let name = "John Doe"; //export IF it is passed in by another file
  let points = 100;
  let showControls = true;

  const consoleLog = value => console.log(value);

  const addPoint = () => (points += 1); //being passed into the button on:click
  const removePoint = () => (points -= 1); //being passed into the button on:click
  const toggleControls = () => (showControls = !showControls); //set showControls boolean to whatever it is NOT at the time, so basically just flips it from true/false and vice versa
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
      <h1>
        {name}
        <button class="btn btn-sm" on:click={toggleControls}>
          {#if showControls}-{:else}+{/if}
        </button>
      </h1>
      <h3>{points}</h3>
      {#if showControls}
        <button class="btn" on:click={addPoint}>+1</button>
        <button class="btn btn-dark" on:click={removePoint}>-1</button>
        <input type="number" bind:value={points} />
      {/if}
    </div>
  </div>

</main>
