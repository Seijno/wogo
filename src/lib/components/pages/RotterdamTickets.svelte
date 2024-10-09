<script>
    import { RotterdamTicketHero, TicketCard } from '$lib/index'
    export let items
  </script>
  
  <svelte:head>
    <title></title>
  </svelte:head>
  
  <RotterdamTicketHero {items} />
  <style>
    h1 {
      color: white;
      font-size: 2rem;
    }
  
  </style>
