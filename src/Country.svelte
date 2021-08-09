<script>
  import City from "./City.svelte";
  export let country, show;

  const { name, capital, continent, currency, emoji, phone, cities } = country;
</script>

<div class="country">
  <h3>Name : {name}</h3>
  <div class="details">
    <p>Capital : {capital}</p>
    <p>Continent : {continent.name}</p>
    <p>Currency : {currency}</p>
    <p>Flag : {emoji}</p>
    <p>Phone : +{phone}</p>
  </div>
  {#if show.cities}
    <div class="options">
      <div class="option">
        <input
          type="checkbox"
          id="city"
          bind:checked={show.citiesOptions.population}
        />

        <label for="city">Show Population </label>
      </div>
      <div class="option">
        <input
          type="checkbox"
          id="city"
          bind:checked={show.citiesOptions.province}
        />

        <label for="city">Show Province </label>
      </div>
      <div class="option">
        <input
          type="checkbox"
          id="city"
          bind:checked={show.citiesOptions.location}
        />

        <label for="city">Show Location </label>
      </div>
    </div>
  {/if}

  {#if show.cities}
    {#each cities.results as city}
      <City show={show.citiesOptions} {city} />
    {/each}
  {/if}
</div>

<style>
  .details {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
  }
  .options,
  .option {
    display: flex;
  }
  .options {
    justify-content: space-between;
    align-items: center;
  }
</style>
