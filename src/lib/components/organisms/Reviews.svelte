<script>
  import { onMount } from 'svelte'
  export let items

  let currentIndex = 0
  let interval

  const hasReviews = items?.[4]?.componentsCollection?.items?.length > 0

  const changeSlide = (index) => {
    currentIndex = index
    resetAutoSlide()
  }

  const resetAutoSlide = () => {
    clearInterval(interval)
    startAutoSlide()
  }

  const startAutoSlide = () => {
    if (hasReviews) {
      interval = setInterval(() => {
        currentIndex = (currentIndex + 1) % items[1].componentsCollection.items.length
      }, 5000)
    }
  }

  onMount(() => {
    if (hasReviews) startAutoSlide()
    return () => clearInterval(interval)
  })
</script>

{#if hasReviews}
  <section class="reviews-section">
    <div class="carousel-wrapper">
      {#each items[4].componentsCollection.items as item, index}
        <article
          class="review-card {currentIndex === index ? 'active' : ''}"
          style="transform: translateX(calc((var(--index, 0) - {currentIndex}) * 100%));"
        >
          <h3>{item.title}</h3>

          <div class="star-rating">
            {#each Array(5) as _, i}
              <span class="star">&#9733;</span>
            {/each}
          </div>

          <blockquote>
            <p>{item.textParagraph}</p>
          </blockquote>
        </article>
      {/each}
    </div>

    <div class="controls" aria-label="Carousel navigation">
      {#each items[1].componentsCollection.items as _, index}
        <button
          class="dot {currentIndex === index ? 'active' : ''}"
          on:click={() => changeSlide(index)}
          aria-label="Go to slide {index + 1}"
        ></button>
      {/each}
    </div>
  </section>
{/if}

<style>
  :root {
    --star-color: #ffffff;
    --text-align: center;
    --text-max-width: 600px;
  }

  .reviews-section {
    position: relative;
    overflow: hidden;
    background-color: var(--cs-midnight-lagoon);
    padding: 2rem 0;
    text-align: var(--text-align);
  }

  .carousel-wrapper {
    display: flex;
    transition: transform 0.5s ease;
  }

  .review-card {
    flex: 0 0 100%;
    max-width: 100%;
    border-radius: 0.5rem;
    padding: 1.5rem;
    transition: opacity 0.5s ease;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  blockquote {
    margin: 0 auto;
    font-size: 1.1rem;
    font-style: italic;
    color: #ffffff;
    max-width: var(--text-max-width);
    line-height: 1.6;
    text-align: left;
  }

  blockquote p {
    margin: 0;
  }

  .star-rating {
    display: flex;
    justify-content: center;
    gap: 0.25rem;
    margin-bottom: 1rem;
  }

  .star {
    font-size: 1.2rem;
    color: var(--star-color);
  }

  .controls {
    display: flex;
    justify-content: center;
    gap: 0.5rem;
    margin-top: 1rem;
  }

  h3 {
    color: #ffffff;
  }

  .dot {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: #ffffff;
    border: none;
    cursor: pointer;
    transition: background 0.3s;
  }

  .dot.active {
    background: var(--cs-tidepool-blue);
  }

  .dot:focus {
    outline: 2px solid var(--cs-sky-glacier);
  }

  @media (max-width: 768px) {
    .review-card {
      padding: 1rem;
    }

    blockquote {
      font-size: 1rem;
    }
  }

  @container (max-width: 600px) {
    blockquote {
      max-width: 90%;
      text-align: center;
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .carousel-wrapper {
      transition: none;
    }

    .review-card {
      transition: none;
    }
  }
</style>
