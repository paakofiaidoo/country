<script>
  export let city, show;
  const { name, population, province, location } = city;
</script>

<div class="city">
  <p>{name}</p>
  {#if show.population}
    <p>Population : {population ? population : "unknown"}</p>
  {/if}
  {#if show.province}
    <p>
      Province : {province ? province : "unknown"}
    </p>
  {/if}
  {#if show.location}
    <p>
      Location:
      <span>
        latitude:{location.latitude}
      </span>
      <span>
        log: {location.longitude}
      </span>
    </p>
  {/if}
</div>

<style>
  .city {
    border: 1px solid #666;
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
  }
  .city:nth-child(even) {
    background-color: #ddd;
  }
</style>
