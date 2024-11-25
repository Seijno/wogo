<script>
  import { Link, Image, Button, ArrowRight } from '$lib/index'
  import logo from '$lib/assets/logo.webp'
  export let footerItems
</script>

<footer>
  <!-- LOGO -->
  <img src={logo} height="50" width="50" alt="Ga naar home" />

  <section>
    <!-- NIEUWSBRIEF -->
    <form>
      <legend>{footerItems[0].newsletterTitle}</legend>
      <p>{footerItems[0].newsLetterDescription}</p>

      <label>
        Email* <!-- wordt nog dynamisch -->

        <!-- dit nog een component makene (molecule)-->
        <input
          type="email"
          name="email"
          placeholder={footerItems[0].placeholderText}
          required
        />
      </label>
      <Button
        type="submit"
        variant="primary"
        title="Abonneer"
        icon={ArrowRight}
        iconColor="var(--btn-primary-text-clr)"
        size="sm"
      />
      <!-- dit nog een component makene (molecule)-->
    </form>

    <!-- Navigatie -->
    <nav>
      <ul>
        <h4>Navigatie</h4> <!-- moet later dynamische content zijn in contentful -->
        {#each footerItems[0].footerLinksCollection.items as item}
          <li>
            <Link href={item.slug} aria-label={item.title} title={item.title} 
            fontSize='1rem' 
            color='var(--txt-primary-clr)' 
            decoration='underline'></Link>
          </li>
        {/each}
      </ul>

      <ul>
        <h4>Bronnen</h4> <!-- moet later dynamische content zijn in contentful -->
        {#each footerItems[0].footerLinksCollection.items as item} <!-- moet later andere links zijn -->
          <li>
            <Link href={item.slug} aria-label={item.title} title={item.title} 
            fontSize='1rem' 
            color='var(--txt-primary-clr)' 
            decoration='underline'></Link>
          </li>
        {/each}
      </ul>

      <ul>
        <h4>Social</h4><!-- moet later dynamische content zijn in contentful -->
        {#each footerItems[0].socialMediaIconsCollection.items as item}
          <li>
            <Link href={item.url} 
            fontSize='1rem' 
            color='var(--txt-primary-clr)' 
            decoration='underline'>
              {item.assetCollection.items[0].title}
            </Link>
          </li>
        {/each}
      </ul>

      <ul>
        <h4>Review ons</h4><!-- moet later dynamische content zijn in contentful -->
        <a href="https://www.tripadvisor.nl/Attraction_Review-g188590-d25182767-Reviews-Cocktail_Walk-Amsterdam_North_Holland_Province.html">
          Tripadvisor
        </a>
        <a href="https://uk.trustpilot.com/review/wogoamsterdam.com?utm_medium=trustbox&utm_source=TrustBoxReviewCollector">
          Trustpilot
        </a>
        <!-- moet later dynamische content zijn in contentful -->
      </ul>
    </nav>
  </section>
  

  <hr>

  <!-- COPYRIGHT -->
  <div>
    <!-- moet later dynamische content zijn in contentful -->
    <p><small>© 2024 WOGO Amsterdam. Alle rechten voorbehouden.</small></p>
    <img src="/2a3b9e_c62852e7512143168afec041916d1f9d~mv2.png.webp" height="26" width="100"  alt="nix 18"> 
  </div>
</footer>

<style>
  /* Mobile  */
  legend,h4 {
    font-family: 'LuloClean', sans-serif;
  }
  footer {
    width: 100%;
    padding: 2em 5vw;
    display: flex;
    flex-direction: column;
    gap: 2em;
    background-color: var(--accent1-tertiary);
    color: var(--txt-tertiary-clr);
  }
  h4 {
    font-size: 1em;
    line-height: 2em;
    margin-bottom: .5em;
  }
  legend {
    font-size: 1.7em;
  }
  form {
    display: grid;
    /* flex-direction: column; */
    gap: 1em;
  }

  input:where([type='email']) {
    display: block;
    margin: 1rem 0;
    font-size: 1rem;
    font-family: inherit;
    padding: 1rem;
    width: 100%;
    border: 0;
    background-color: var(--accent2-quaternary);
    border-radius: 10px;
  }

  input::placeholder {
    color: var(--accent1-tertiary);
  }

  nav {
    display: flex;
    flex-wrap: wrap;
    gap: 2em 5em;
    justify-content: space-between;
  }

  section {
    display: flex;
    flex-direction: column;
    gap: 2em;
  }

  ul {
    list-style: none;
  }

  ul li a {
    background-color: var(--accent1-tertiary);
  }

  div {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  hr {
    height: .5px;
    border: 0;
    background-color: var(--accent2-quaternary);
  }


  /* Desktop */
  @media screen and (min-width: 48em) {
    nav {
      flex-wrap: nowrap;
    }

    form {
      min-width: 20em;
      width: 30em;
    }

    section {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 5em;
      width: 100%;
    }
  }
</style>
