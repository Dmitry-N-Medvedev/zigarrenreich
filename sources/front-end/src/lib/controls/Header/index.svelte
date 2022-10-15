<script>
  import {
    page,
  } from '$app/stores';
  import Logo from '$lib/controls/Logo/index.svelte';
</script>

<style>
  header,
  header > nav {
    display: flex;
    justify-content: center;
    align-items: center;

    height: var(--header-height);

    background-color: var(--header-background-color);
  }

  header > nav > a {
    /* aspect-ratio: var(--header-nav-aspect-ratio); */
    display: flex;
    justify-content: center;
    align-items: center;

    height: 100%;
    padding: 0 1vw;

    text-decoration: none;

    pointer-events: all;
    cursor: pointer;
  }

  header > nav > a:not(:first-of-type) {
    margin: 0 0.5vw;
  }

  header > nav > a:link {
    color: var(--main-color);
  }

  header > nav > a:hover {
    color: var(--main-color);
  }

  header > nav > a:active {
    color: var(--main-color);
  }

  header > nav > a:visited {
    color: var(--main-color);
  }

  .active_link {
    color: red !important;
  }
</style>

<header>
  <nav data-sveltekit-prefetch>
    <a href='/about-us' class:active_link={ $page.url.pathname === '/about-us' }>about us</a>
    <a href='/store-and-lounge' class:active_link={ $page.url.pathname === '/store-and-lounge' }>store & lounge</a>
    <a href='/'><Logo /></a>
    <a href='/gallery' class:active_link={ $page.url.pathname === '/gallery' }>gallery</a>
    <a href='/lexicon' class:active_link={ $page.url.pathname === '/lexicon' }>lexicon</a>
    <a href='/contacts' class:active_link={ $page.url.pathname === '/contacts' }>contacts</a>
  </nav>
</header>