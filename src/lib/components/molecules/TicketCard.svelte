<script>
  import { Image, RouteIcon, CocktailIcon, Button } from '$lib/index'
  export let itemCollection
  const items = itemCollection.componentsCollection.items
</script>

<div class="ticket-container">
  {#each items as item}
    <article class="ticket-card">
      <div class="card-header">
        <h3>{item.title}</h3>
        <Image
          src={item.image.url}
          alt={item.image.title}
          brdRadius="var(--radius-lg)"
          opacity="0.6"
          loading="lazy"
        />
      </div>

      <div class="card-body">
        <p>
          <span><RouteIcon width="25" height="25" fill="var(--page-bg-color)" /></span>
          {item.location}
        </p>

        <p>
          <span><CocktailIcon width="25" height="25" fill="var(--page-bg-color)" /></span>
          {item.cocktailDescription}
        </p>

        <div class="button-group">
          <Button type="button" variant="primary" title="Book Now" size="m" />
          <Button href="/home/{item.slug}" variant="secondary" title="Read More" size="m" />
        </div>
      </div>
    </article>
  {/each}
</div>

<style>
  .ticket-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
    padding: 2rem;
  }

  article {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    background-color: var(--accent2-quaternary);
    border-radius: var(--radius-lg);
    padding: 1rem;
    gap: 1rem;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }

  .card-header {
    position: relative;
    text-align: center;
  }

  .card-header h3 {
    margin: 0;
    padding: 0.5rem;
    font-size: var(--fs-md);
    line-height: 1.2em;
    color: var(--txt-quaternary-clr);
    text-shadow: 1px 1px var(--btn-secondary-bg);
  }

  .card-header p {
    position: absolute;
    left: 1rem;
    top: 1rem;
    padding: 0.3rem 0.6rem;
    font-size: var(--fs-sm);
    font-weight: 600;
    background-color: var(--btn-secondary-bg);
    color: var(--btn-primary-text-clr);
    border-radius: var(--radius-lg);
  }

  .card-body {
    display: flex;
    flex-direction: column;
    gap: 0.8rem;
  }

  .card-body p {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    font-size: var(--fs-sm);
    color: var(--txt-dark-clr);
  }

  .button-group {
    display: flex;
    justify-content: space-between;
    gap: 0.5rem;
  }

  @media screen and (min-width: 48em) {
    .ticket-container {
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    }

    article {
      padding: 1.5rem;
    }

    .card-header h3 {
      font-size: var(--fs-lg);
    }

    .card-body p {
      font-size: var(--fs-md);
    }
  }
</style>
