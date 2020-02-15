<script>
  import { createEventDispatcher } from "svelte";

  let showControls = false;

  export let name; //this is exported because props are being passed in for this value
  export let points; //this is exported because props are being passed in for this value

  const dispatch = createEventDispatcher();

  const addPoint = () => (points += 1); //being passed into the button on:click
  const removePoint = () => (points -= 1); //being passed into the button on:click
  const toggleControls = () => (showControls = !showControls); //set showControls boolean to whatever it is NOT at the time, so basically just flips it from true/false and vice versa
  const onDelete = e => {
    e.preventDefault();
    dispatch("removeplayer", name);
  };
</script>

<style>
  h1 {
    color: #204f6e;
  }
</style>

<div class="container">
  <div class="card">
    <h1>
      {name}
      <button class="btn btn-sm" on:click={toggleControls}>
        {#if showControls}-{:else}+{/if}
      </button>
      <button class="btn btn-sm float-right delete-button" on:click={onDelete}>
        <i class="fas fa-times-circle" />
      </button>
    </h1>
    <h3>Points: {points}</h3>
    {#if showControls}
      <button class="btn" on:click={addPoint}>+1</button>
      <button class="btn btn-dark" on:click={removePoint}>-1</button>
      <input type="number" bind:value={points} />
    {/if}

  </div>
</div>
