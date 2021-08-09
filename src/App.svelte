<script>
  export let countries;
  let selectedCountry = "",
    selectedContinent = null;

  const countryData = (countId) => {
    return countries.filter((id) => id !== countId)[0];
  };
</script>

<main>
  <h1>country</h1>
  <!-- <div class="selection">
    <label for="continet">Choose a continent</label>
    <select name="continet" id="continet" bind:value={selectedContinent}>
      <option value="" disabled selected>Select your option</option>
      {#each countries as { continent }}
        <option value={continent.id}>{continent.name}</option>
      {/each}
    </select>
  </div> -->
  <div class="selection">
    <label for="country">Choose a country</label>
    <select name="country" id="country" bind:value={selectedCountry}>
      <option value="" disabled selected>Select your option</option>
      {#each countries as { name, id }}
        <option value={id}>{name}</option>
      {/each}
    </select>
  </div>

  <div class="options">
    <div class="option">
      <input type="checkbox" id="city" value="city" />
      <label for="city">city</label>
    </div>
  </div>

  <div class="output">
    {#if selectedCountry !== ""}
      <div>
        {console.log( countryData(selectedCountry))}
      </div>
    {:else}
      <p>chose a country</p>
    {/if}
  </div>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }
  .option,
  .selection {
    display: flex;
    justify-content: center;
    align-items: center;
    align-content: center;
    padding: 1rem;
  }
  label {
    margin: 1rem;
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
