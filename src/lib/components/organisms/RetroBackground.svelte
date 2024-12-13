<script>
  // This component animates the retro line art vertically.
</script>

<div class="retro-background"></div>

<style>
  .retro-background {
    position: fixed;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 200px;
    height: 100%;
    background: linear-gradient(to bottom, transparent, hsl(45, 85%, 60%) 20%, transparent 40%);
    background-repeat: repeat-y;
    animation: move-vertical 10s linear infinite;
    z-index: 0;
  }

  @keyframes move-vertical {
    0% {
      background-position: 0 0;
    }
    100% {
      background-position: 0 -200%;
    }
  }
</style>
