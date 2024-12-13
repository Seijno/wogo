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
        <div class="image-container">
          <Image
            src={item.image.url}
            alt={item.image.title}
            brdRadius="var(--radius-lg)"
            opacity="0.6"
            loading="lazy"
          />
          <div class="image-overlay">
            <a href="#view-{item.title}" class="view-link">View</a>
          </div>
        </div>
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

    <!-- Fullscreen Modal -->
    <div id="view-{item.title}" class="image-modal">
      <div class="modal-content">
        <div class="retro-lines">
          <Image src={item.image.url} alt={item.image.title} brdRadius="0" loading="lazy" />
        </div>
        <a href="#" class="close-button">✕</a>
      </div>
    </div>
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

  .image-container {
    position: relative;
    cursor: pointer;
  }

  .image-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    background: rgba(0, 0, 0, 0.5);
    opacity: 0;
    border-radius: var(--radius-lg);
    transition: opacity 0.3s ease-in-out;
  }

  .image-container:hover .image-overlay {
    opacity: 1;
  }

  .view-link {
    color: #fff;
    font-size: var(--fs-md);
    font-weight: bold;
    text-decoration: none;
    background: var(--btn-primary-bg);
    padding: 0.5rem 1rem;
    border-radius: var(--radius-lg);
  }

  .image-modal {
    position: fixed;
    inset: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    background: rgba(0, 0, 0, 0.8);
    z-index: 1000;
    visibility: hidden;
    opacity: 0;
    transition:
      opacity 0.5s ease-in-out,
      visibility 0.5s ease-in-out;
  }

  .image-modal:target {
    visibility: visible;
    opacity: 1;
  }

  .modal-content {
    position: relative;
    animation: retro-wiggle 2s infinite;
  }

  .retro-lines {
    display: inline-block;
    position: relative;
    padding: 1rem;
    background: radial-gradient(circle, #ffcc00, #ff0066);
    animation: retro-lines-animation 2s ease-in-out infinite;
  }

  .retro-lines img {
    max-width: 90vw;
    max-height: 90vh;
    border-radius: var(--radius-lg);
    position: relative;
    z-index: 10;
  }

  .close-button {
    position: absolute;
    top: 1rem;
    right: 1rem;
    font-size: 2rem;
    color: white;
    text-decoration: none;
    background: var(--btn-secondary-bg);
    border-radius: 50%;
    padding: 0.3rem;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.5);
    z-index: 20;
  }

  @keyframes retro-wiggle {
    0%,
    100% {
      transform: rotate(0deg);
    }
    25% {
      transform: rotate(2deg);
    }
    50% {
      transform: rotate(-2deg);
    }
    75% {
      transform: rotate(1deg);
    }
  }

  @keyframes retro-lines-animation {
    0% {
      clip-path: polygon(0% 0%, 100% 0%, 100% 0%, 0% 0%);
    }
    25% {
      clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 90% 100%);
    }
    50% {
      clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 0% 90%);
    }
    75% {
      clip-path: polygon(10% 10%, 90% 10%, 80% 90%, 10% 80%);
    }
    100% {
      clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 0% 0%);
    }
  }
</style>
