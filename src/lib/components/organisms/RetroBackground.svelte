<script>
  let scrollY = 0

  // Listen to the scroll event to update the scrollY value.
  window.addEventListener('scroll', () => {
    scrollY = window.scrollY
    const vertical = document.querySelector('.retro-path-vertical')
    const horizontal = document.querySelector('.retro-path-horizontal')

    // Adjust the background position based on scrollY.
    vertical.style.backgroundPosition = `0 ${-scrollY * 0.5}px`
    horizontal.style.backgroundPosition = `${-scrollY * 0.3}px 0`
  })
</script>

<div class="retro-path-vertical"></div>
<div class="retro-path-horizontal"></div>

<style>
  body {
    margin: 0;
    background-color: white;
    overflow-x: hidden;
  }

  .retro-path-vertical {
    position: fixed;
    top: 0;
    right: 10%;
    width: 500px;
    height: 300%;
    background: repeating-linear-gradient(
      to bottom,
      hsl(45, 85%, 60%) 0%,
      hsl(300, 85%, 70%) 25%,
      hsl(120, 85%, 60%) 50%,
      hsl(180, 85%, 70%) 75%,
      hsl(45, 85%, 60%) 100%
    );
    -webkit-mask-image: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='200' height='3000'><path d='M50 0 Q100 200 50 400 Q0 600 50 800 Q100 1000 50 1200' stroke='black' stroke-width='30' fill='none'/></svg>");
    mask-image: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='200' height='3000'><path d='M50 0 Q100 200 50 400 Q0 600 50 800 Q100 1000 50 1200' stroke='black' stroke-width='30' fill='none'/></svg>");
    -webkit-mask-repeat: repeat-y;
    mask-repeat: repeat-y;
    z-index: 0;
  }

  /* Thicker and animated horizontal retro path */
  .retro-path-horizontal {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 300%;
    height: 200px; /* Increased height for a thicker line */
    background: repeating-linear-gradient(
      to right,
      hsl(45, 85%, 60%) 0%,
      hsl(300, 85%, 70%) 25%,
      hsl(120, 85%, 60%) 50%,
      hsl(180, 85%, 70%) 75%,
      hsl(45, 85%, 60%) 100%
    );
    -webkit-mask-image: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='3000' height='200'><path d='M0 50 Q400 100 800 50 Q1200 0 1600 50 Q2000 100 2400 50' stroke='black' stroke-width='30' fill='none'/></svg>");
    mask-image: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='3000' height='200'><path d='M0 50 Q400 100 800 50 Q1200 0 1600 50 Q2000 100 2400 50' stroke='black' stroke-width='30' fill='none'/></svg>");
    -webkit-mask-repeat: repeat-x;
    mask-repeat: repeat-x;
    z-index: 0;
  }
</style>
