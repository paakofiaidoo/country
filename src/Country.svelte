<script>
  export let country;
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
  {#each cities.results as { name, population, province, location }}
    <div class="city">
      <p>{name}</p>
      <p>Population : {population ? population : "unknown"}</p>
      <p>
        Province : {province ? province : "unknown"}
      </p>
      <p>
        Location:
        <span>
          latitude:{location.latitude}
        </span>
        <span>
          log: {location.longitude}
        </span>
      </p>
    </div>
  {/each}
</div>

<style>
  .details {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
  }
  .city {
    border: 1px solid #666;
  }
  .city:nth-child(even) {
    background-color: #ddd;
  }
</style>
