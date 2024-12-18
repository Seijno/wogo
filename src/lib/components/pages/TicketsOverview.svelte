<script>
  import { Filter, TicketCard } from '$lib/index'
  import { onMount } from 'svelte'
  export let itemCollection
  export let cities

  onMount(() => {
    const piano = document.getElementById('piano'),
      metal = document.getElementById('metal'),
      bell = document.getElementById('bellSound'),
      tree = document.getElementById('tree'),
      root = document.querySelector(':root'),
      krampusbells = document.querySelectorAll('.krampusbell'),
      merryChristmas = document.getElementById('curtain')

    let klikteller = 0

    tree.addEventListener('click', action)

    krampusbells.forEach((krampusbell) => {
      krampusbell.addEventListener('mouseover', noise)
    })

    function action() {
      klikteller++

      if (klikteller === 1) {
        setTimeout(() => {
          root.classList.toggle('darkmode')
        }, 3000)

        curtain()
        metal.play()
      } else if (!metal.paused) {
        metal.pause()
        metal.currentTime = 0
        piano.play()
        root.classList.toggle('darkmode')
        console.log(1)
      } else if (!piano.paused) {
        piano.pause()
        piano.currentTime = 0
        metal.play()
        root.classList.toggle('darkmode')
        console.log(2)
      }
    }
    function pianoSong() {
      piano.play()
      metal.pause()
    }
    function noise() {
      bell.play()
    }
    function curtain() {
      merryChristmas.style.display = 'block'
      merryChristmas.classList.toggle('animation')
    }
  })
</script>

<section>
  <section>
    <h1>Tickets</h1>
    <Filter {cities} />
  </section>

  <section>
    <TicketCard {itemCollection} />
  </section>
</section>

<svelte:head>
  <title></title>
</svelte:head>
<div id="curtain">Merry Christmas</div>
<div class="snowflake">❅</div>
<div class="snowflake">❅</div>
<div class="snowflake">❆</div>
<div class="snowflake">❄</div>
<div class="snowflake">❅</div>
<div class="snowflake">❆</div>
<div class="snowflake">❄</div>
<div class="snowflake">❅</div>
<div class="snowflake">❆</div>
<div class="snowflake">❄</div>
<img id="tree" src="/src/lib/assets/tree.png" alt="kerstboom" />
<img id="krampus" src="/src/lib/assets/krampus.png" alt="krampus" />
<img id="bell" class="krampusbell" src="/src/lib/assets/krampusbellpin.webp" alt="krampus bell" />
<img id="bell1" class="krampusbell" src="/src/lib/assets/krampusbellpin.webp" alt="krampus bell" />
<img id="bell2" class="krampusbell" src="/src/lib/assets/krampusbellpin.webp" alt="krampus bell" />
<audio id="piano" src="/src/lib/assets/piano.mp3"></audio>
<audio id="metal" src="/src/lib/assets/metal.mp3"></audio>
<audio id="bellSound" src="/src/lib/assets/sleigh-bell-long-01-38409.mp3"></audio>

<style>
  @font-face {
    font-family: 'rusty-attack';
    src: url('/src/lib/assets/font/RUSTY\ ATTACK\ DEMO\ Regular.otf');
  }
  h1 {
    color: white;
    font-size: 3.5rem;
  }
  #curtain {
    display: none;
    position: fixed;
    top: 0;
    left: -100vw;
    width: 100vw;
    height: 100vh;
    background: black;
    color: red;
    z-index: 1001;
    text-align: center;
    line-height: 100vh;
    font-size: 7rem;
    font-family: 'rusty-attack';
  }
  :global(.animation) {
    animation: trick 5s forwards;
  }
  @keyframes trick {
    0% {
      left: -100vw;
    }
    30% {
      left: 0;
    }
    60% {
      left: 0;
    }
    100% {
      left: 100vw;
      display: none;
    }
  }
  #krampus {
    position: fixed;
    width: 30rem;
    top: 40%;
    right: -25rem;
    rotate: -15deg;
    transition: 1.5s ease-in-out;
    animation-name: rotate;
    animation-timeline: scroll();
  }
  .krampusbell {
    display: none;
    position: absolute;
    width: 15rem;
    transition: 0.2s;
    animation: bellShaking infinite 5s;
  }
  @keyframes bellShaking {
    0% {
      rotate: 0deg;
    }
    20% {
      rotate: 20deg;
    }
    40% {
      rotate: -20deg;
    }
    60% {
      rotate: 20deg;
    }
    80% {
      rotate: -20deg;
    }
    100% {
      rotate: 0deg;
    }
  }
  #bell {
    left: 10vw;
    top: 40rem;
  }
  #bell1 {
    top: 5rem;
    right: 9rem;
  }
  #bell2 {
    left: 8rem;
  }

  #tree {
    position: fixed;
    width: 3rem;
    top: 1rem;
    right: 6rem;
    z-index: 1000;
    cursor: pointer;
  }
  @keyframes rotate {
    0% {
      rotate: -10deg;
    }
    10% {
      rotate: -40deg;
    }
    20% {
      rotate: -10deg;
    }
    30% {
      rotate: -40deg;
    }
    40% {
      rotate: -10deg;
    }
    50% {
      rotate: -40deg;
    }
    60% {
      rotate: -10deg;
    }
    70% {
      rotate: -40deg;
    }
    80% {
      rotate: -10deg;
    }
    90% {
      rotate: -40deg;
    }
    100% {
      rotate: -10deg;
    }
  }
  #tree:hover {
    animation: shuffle infinite 1s;
  }

  @keyframes shuffle {
    0% {
      rotate: 0deg;
    }
    25% {
      rotate: 15deg;
    }
    50% {
      rotate: -15deg;
    }
    100% {
      rotate: 0deg;
    }
  }

  section:first-child {
    margin: 7rem 4rem 4rem 4rem;
  }

  section:first-child > section:last-child {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    justify-content: center;
  }
  :global(body) {
    background: var(--page-bg-color);
  }
  .snowflake {
    color: #fff;
    font-size: 1em;
    font-family: Arial;
    text-shadow: 0 0 1px #000;
  }

  @-webkit-keyframes snowflakes-fall {
    0% {
      top: -10%;
    }
    100% {
      top: 100%;
    }
  }
  @-webkit-keyframes snowflakes-shake {
    0% {
      -webkit-transform: translateX(0px);
      transform: translateX(0px);
    }
    50% {
      -webkit-transform: translateX(80px);
      transform: translateX(80px);
    }
    100% {
      -webkit-transform: translateX(0px);
      transform: translateX(0px);
    }
  }
  @keyframes snowflakes-fall {
    0% {
      top: -10%;
    }
    100% {
      top: 100%;
    }
  }
  @keyframes snowflakes-shake {
    0% {
      transform: translateX(0px);
    }
    50% {
      transform: translateX(80px);
    }
    100% {
      transform: translateX(0px);
    }
  }
  .snowflake {
    position: fixed;
    top: -10%;
    z-index: 9999;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    cursor: default;
    -webkit-animation-name: snowflakes-fall, snowflakes-shake;
    -webkit-animation-duration: 10s, 3s;
    -webkit-animation-timing-function: linear, ease-in-out;
    -webkit-animation-iteration-count: infinite, infinite;
    -webkit-animation-play-state: running, running;
    animation-name: snowflakes-fall, snowflakes-shake;
    animation-duration: 10s, 3s;
    animation-timing-function: linear, ease-in-out;
    animation-iteration-count: infinite, infinite;
    animation-play-state: running, running;
  }
  .snowflake:nth-of-type(0) {
    left: 1%;
    -webkit-animation-delay: 0s, 0s;
    animation-delay: 0s, 0s;
  }
  .snowflake:nth-of-type(1) {
    left: 10%;
    -webkit-animation-delay: 1s, 1s;
    animation-delay: 1s, 1s;
  }
  .snowflake:nth-of-type(2) {
    left: 20%;
    -webkit-animation-delay: 6s, 0.5s;
    animation-delay: 6s, 0.5s;
  }
  .snowflake:nth-of-type(3) {
    left: 30%;
    -webkit-animation-delay: 4s, 2s;
    animation-delay: 4s, 2s;
  }
  .snowflake:nth-of-type(4) {
    left: 40%;
    -webkit-animation-delay: 2s, 2s;
    animation-delay: 2s, 2s;
  }
  .snowflake:nth-of-type(5) {
    left: 50%;
    -webkit-animation-delay: 8s, 3s;
    animation-delay: 8s, 3s;
  }
  .snowflake:nth-of-type(6) {
    left: 60%;
    -webkit-animation-delay: 6s, 2s;
    animation-delay: 6s, 2s;
  }
  .snowflake:nth-of-type(7) {
    left: 70%;
    -webkit-animation-delay: 2.5s, 1s;
    animation-delay: 2.5s, 1s;
  }
  .snowflake:nth-of-type(8) {
    left: 80%;
    -webkit-animation-delay: 1s, 0s;
    animation-delay: 1s, 0s;
  }
  .snowflake:nth-of-type(9) {
    left: 90%;
    -webkit-animation-delay: 3s, 1.5s;
    animation-delay: 3s, 1.5s;
  }
</style>
