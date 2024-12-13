<script>
  import { page } from '$app/stores'
  import { onMount } from 'svelte'

  let filter = []
  export let cities = []

  onMount(() => {
    const urlSearchParams = new URLSearchParams($page.url.search)
    filter = urlSearchParams.getAll('locatie') || []
  })

  function applyFilter(event) {
    event.preventDefault()
    const formData = new FormData(event.target)
    const locatie = formData.get('locatie')
    const url = new URL(window.location)

    if (locatie) {
      url.searchParams.set('locatie', locatie)
    } else {
      url.searchParams.delete('locatie')
    }

    window.location.href = url
  }
</script>

<section>
  <form on:submit={applyFilter}>
    <select name="locatie" id="locatie-select" tabindex="0">
      <option value="" selected={!filter.length}>All Locations</option>
      {#each cities as city}
        <option value={city} selected={filter.includes(city)}>
          {city}
        </option>
      {/each}
    </select>
    <button type="submit" class="retro-button">Apply Filter</button>
  </form>
</section>

<style>
  section {
    margin: 2rem 0;
    color: white;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  form {
    display: flex;
    gap: 1rem;
  }

  select {
    padding: 0.5rem;
    border: none;
    background-color: #444;
    color: #fff;
    text-transform: uppercase;
    border-radius: 0.8rem;
  }

  button {
    padding: 0.5rem 1rem;
    background-color: #fff;
    color: #444;
    border: none;
    border-radius: 0.8rem;
    font-weight: bold;
    text-transform: uppercase;
    cursor: pointer;
    transition: transform 0.3s ease;
  }

  button:hover {
    transform: scale(1.05);
  }

  button:active {
    transform: scale(0.95);
  }
</style>
