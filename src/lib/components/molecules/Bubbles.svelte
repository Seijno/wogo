<script>
  import { onMount } from 'svelte'

  onMount(() => {
    // Selecteer alle elementen met de class 'random-top'
    const elements = document.querySelectorAll('div')

    // Definieer het bereik voor de willekeurige waarden
    const minTop = 10 // Minimum hoogte
    const maxTop = 126 // Maximum hoogte

    // Voeg willekeurige top-waarden toe
    elements.forEach((element) => {
      // Genereer een waarde tussen minTop en maxTop
      const randomTop = Math.floor(Math.random() * (maxTop - minTop + 1)) + minTop
      element.style.top = `${randomTop}%`
    })
  })
</script>

<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>

<style>
  div {
    position: absolute;
    width: 1.5rem;
    height: 1.5rem;
    background: white;
    border-radius: 3rem;
    animation: colorchange forwards;
    animation-timeline: scroll();
  }
  div:nth-child(1) {
    left: 0;
    margin-bottom: 5rem;
  }
  div:nth-child(2) {
    left: 5%;
  }
  div:nth-child(3) {
    left: 10%;
    top: 90%;
  }
  div:nth-child(4) {
    left: 15%;
  }
  div:nth-child(5) {
    left: 20%;
  }
  div:nth-child(6) {
    left: 25%;
  }
  div:nth-child(7) {
    left: 30%;
  }
  div:nth-child(8) {
    left: 35%;
  }
  div:nth-child(9) {
    left: 40%;
  }
  div:nth-child(10) {
    left: 45%;
  }
  div:nth-child(11) {
    left: 50%;
  }
  div:nth-child(12) {
    left: 55%;
  }
  div:nth-child(13) {
    left: 60%;
  }
  div:nth-child(14) {
    left: 65%;
  }
  div:nth-child(15) {
    left: 70%;
  }
  div:nth-child(16) {
    left: 75%;
  }
  div:nth-child(17) {
    left: 80%;
  }
  div:nth-child(18) {
    left: 85%;
  }
  div:nth-child(19) {
    left: 90%;
  }
  div:nth-child(20) {
    left: 95%;
  }
  div:nth-child(21) {
    left: 100%;
  }

  @keyframes colorchange {
    0% {
      background: yellow;
    }
    20% {
      background: green;
    }
    40% {
      background: blue;
    }
    60% {
      background: purple;
    }
    80% {
      background: red;
    }
    100% {
      background: orange;
    }
  }
</style>
