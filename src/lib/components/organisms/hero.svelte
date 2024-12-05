<script>
  import { Button, ArrowRight } from '$lib/index'
  export let items
</script>

<section>
  <div class="futuristic-bg"></div>
  <div class="hero-content">
    <h1>
      {items[0].title}
      <Button
        variant="primary"
        title="book now"
        icon={ArrowRight}
        iconColor="var(--btn-primary-text-clr)"
        size="lg"
      />
    </h1>
    <p>{items[0].subtitle}</p>
  </div>
</section>

<style>
  section {
    display: grid;
    place-items: center;
    position: relative;
    height: 55vh;
    overflow: hidden;
  }

  .futuristic-bg {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(
      130deg,
      rgba(2, 0, 36, 0.8),
      rgba(9, 121, 242, 0.8),
      rgba(0, 212, 255, 0.8),
      rgba(255, 0, 255, 0.8),
      rgba(255, 255, 0, 0.8),
      rgba(0, 245, 212, 0.8)
    );
    background-size: 400% 400%;
    animation: futuristic-animation 5s linear infinite;
    filter: brightness(1.1) contrast(1.2) saturate(1.3);
    z-index: -1;
  }

  @keyframes futuristic-animation {
    0% {
      background-position: 0% 0%;
    }
    25% {
      background-position: 50% 50%;
    }
    50% {
      background-position: 100% 50%;
    }
    75% {
      background-position: 50% 100%;
    }
    100% {
      background-position: 0% 0%;
    }
  }

  .hero-content {
    padding: 1rem;
    margin-top: 3rem;
    font-weight: 700;
    color: #fff;
    text-align: center;
    text-shadow: 0 0 20px rgba(255, 255, 255, 0.8), 0 0 30px rgba(0, 212, 255, 0.6);
  }

  h1 {
    position: relative;
    display: inline-block;
    font-weight: 700;
    font-size: clamp(2.648rem, 6vw, 4.241rem);
    letter-spacing: -1px;
    filter: drop-shadow(0 0 0.4rem #000);
    animation: heading 3s forwards;
  }

  @keyframes heading {
    0% {
      top: -200px;
    }
    100% {
      top: -2px;
    }
  }

  p {
    font-size: 1.5rem;
    font-weight: 700;
    letter-spacing: 0.2rem;
    padding: 0.5rem;
    text-transform: lowercase;
    text-shadow: 0 0 15px rgba(255, 255, 255, 0.8), 0 0 25px rgba(255, 0, 255, 0.6);
    position: relative;
    animation: content 3s forwards;
  }

  @keyframes content {
    0% {
      left: -1000px;
    }
    100% {
      left: 0px;
    }
  }

  @media (min-width: 30em) {
    section {
      height: 70vh;
    }

    .hero-content {
      max-width: 45rem;
    }

    h1 {
      font-size: 70px;
    }
  }
</style>
