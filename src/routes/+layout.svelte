<script>
  import './layout.css';
  import Footer from '$lib/components/Footer.svelte';

  let { children } = $props();

  const pageTitle = 'Beta Readers Needed: Fragile Gamete of Resistance by MVC';
  const pageDescription =
    'Signup form to beta read Michael V. Colianna’s book, “Fragile Gamete of Resistance” – adult science-fiction featuring a Deaf main character and infertility awareness.';
  const pageCard =
    'https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/1200x630';
</script>

<svelte:head>
  <title>{pageTitle}</title>
  <meta name="description" content={pageDescription} />
  <meta property="og:url" content="https://beta-read.mvc.ink" />
  <meta property="og:type" content="website" />
  <meta property="og:title" content={pageTitle} />
  <meta property="og:description" content={pageDescription} />
  <meta property="og:image" content={pageCard} />
</svelte:head>

<main class={['min-h-screen', 'bg-background']}>
  {@render children?.()}

  <Footer />
</main>
