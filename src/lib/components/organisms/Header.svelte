<script>
  import { Link, CartIcon, ArrowDown, Button } from '$lib/index'
  import logo from '$lib/assets/logo.webp'
  export let navigation
</script>

<header>
  <span class="skip-link">
    <Button
      variant="primary"
      href="#content"
      title="skip to content"
      size="lg"
      aria-label="skip to content"
      data-sveltekit-preload-data="false"
    />
  </span>
  <img src={logo} height="70" width="70" alt="Wogo Logo" />
  <button type="button" id="mainMenuOpen" tabindex="-1" aria-label="hamburger-button"
    ><span></span></button
  >
  <nav>
    <ul>
      {#each navigation.navigationLinksCollection.items as link}
        {#if link.title === 'More'}
          <li class="more-button">
            <Button variant="primary" title="more" icon={ArrowDown} size="m" />
            <ul class="more-dropdown">
              {#each link.subLinksCollection.items as sublink}
                <li>
                  <Link
                    href={sublink.slug}
                    title={sublink.title}
                    aria-label={sublink.label}
                    color="var(--txt-dark-clr)"
                  />
                </li>
              {/each}
            </ul>
          </li>
        {:else}
          <li>
            <Link
              href={link.slug}
              title={link.title}
              arialabel={link.label}
              color="var(--txt-secondary-clr)"
              filter="var(--filter-drop)"
            />
            {#if link.subLinksCollection.items.length > 0}
              <ul class="sub-menu" aria-label="Submenu">
                {#each link.subLinksCollection.items as sublink}
                  <li>
                    <Link
                      href={sublink.slug}
                      title={sublink.title}
                      aria-label={sublink.label}
                      color="var(--txt-dark-clr)"
                    />
                  </li>
                {/each}
              </ul>
            {/if}
          </li>
        {/if}
      {/each}
    </ul>
  </nav>
  <div class="button-cart-container">
    <CartIcon width="60px" height="60px" fill="var(--accent2-primary)" />
  </div>
</header>

<style>
  .skip-link {
    position: absolute;
    left: -9999px;
    z-index: 999;
    padding: 1em;
    opacity: 0;
  }

  .skip-link:focus-within {
    left: 50%;
    transform: translateX(-50%);
    opacity: 1;
  }

  header {
    display: flex;
    position: sticky;
    background-color: #221714;
    top: 0;
    right: 0;
    left: 0;
    justify-content: space-between;
    align-items: center;
    padding: 0.5rem 1rem;
    gap: 1.5rem;
    z-index: 900;
  }

  #mainMenuOpen {
    display: none;
  }

  nav li:focus-within .sub-menu,
  nav li:hover .sub-menu {
    display: flex;
    opacity: 1;
  }

  nav li {
    position: relative;
    font-size: var(--fs-lg);
    text-transform: lowercase;
    padding: 0.5rem 1rem;
  }
  nav li:last-of-type {
    margin-left: 5px;
  }

  nav ul > li {
    display: inline-block;
  }

  .more-button {
    position: relative;
  }

  .more-dropdown {
    display: none;
    position: absolute;
    top: 150%;
    left: 0;
    background-color: var(--accent2-tertiary);
    border-radius: var(--radius-md);
    overflow: hidden;
    opacity: 0;
    transform: translateY(-10px);
    transition:
      opacity 0.3s ease,
      transform 0.3s ease;
  }

  .more-button:focus-within .more-dropdown,
  .more-button:hover .more-dropdown {
    display: block;
    opacity: 1;
  }

  .more-dropdown li {
    display: block;
    white-space: nowrap;
  }

  .sub-menu {
    display: flex;
    flex-direction: column;
    position: absolute;
    width: max-content;
    right: 1rem;
    padding: 1rem 0;
    opacity: 0;
    background-color: var(--page-bg-color);
  }

  li:focus-within > .sub-menu {
    display: block;
  }

  .sub-menu .sub-menu li {
    display: flex;
  }

  .button-cart-container {
    display: flex;
    align-items: center;
    position: relative;
    top: 0;
    right: 20px;
    gap: 2rem;
  }

  @media (max-width: 65em) {
    header {
      justify-content: 0;
    }

    #mainMenuOpen {
      display: block;
      width: 40px;
      height: 3px;
      flex-grow: 0;
      border: 0;
      background: transparent;
      cursor: pointer;
      order: 4;
    }

    #mainMenuOpen span,
    #mainMenuOpen span::before,
    #mainMenuOpen span::after {
      display: block;
      position: absolute;
      content: '';
      width: 40px;
      height: 3px;
      background: var(--accent2-primary);
      border-radius: var(--radius-lg);
    }
    #mainMenuOpen span::before {
      margin-top: -12px;
    }

    #mainMenuOpen span::after {
      margin-top: 12px;
    }

    #mainMenuOpen::before {
      top: -8px;
    }

    #mainMenuOpen + nav {
      position: fixed;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      overflow: auto;
      display: flex;
      align-items: center;
      justify-content: center;
      opacity: 0;
      background: var(--page-bg-color);
      transition:
        top 2s 0.5s,
        opacity 0.5s;
    }
    #mainMenuOpen:focus + nav,
    #mainMenuOpen + nav:focus-within {
      left: 0;
      opacity: 1;
      transition:
        top 0s,
        opacity 0.5s;
    }

    #mainMenuOpen + nav li {
      display: flex;
      flex-direction: column;
      font-size: var(--fs-xl);
      padding: 1rem 0 1rem 0;
    }

    #mainMenuOpen + nav > ul:after {
      content: '\2715';
      color: var(--txt-primary-clr);
      display: block;
      position: absolute;
      top: 1.5rem;
      right: 1.2rem;
      font-size: 2.5rem;
      cursor: pointer;
    }

    div {
      display: flex;
      align-items: center;
      gap: 1rem;
      position: relative;
      top: 5px;
    }
  }
</style>
