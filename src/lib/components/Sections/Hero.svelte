<script>
  import HeroBackground from '$lib/components/HeroBackground.svelte';
</script>

<section class={['relative', 'w-full', 'overflow-hidden', 'bg-card-foreground']}>
  <HeroBackground />

  <div class={['relative', 'section-container', 'py-8', 'md:py-16']}>
    <figure class={['relative', 'overflow-hidden', 'rounded-lg', 'md:rounded-2xl']}>
      <img
        sizes="(max-width: 824px) 100vw, 824px"
        srcset="
          https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/200x0 200w,
          https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/498x0 498w,
          https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/698x0 698w,
          https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/824x0 824w"
        src="https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/824x0"
        alt="Illustration of several battle-hardened resistance fighters in front of a space ship (by Jaroslaw Marcinek)"
        fetchpriority="high"
        height="458"
        width="824"
        class={['hidden', 'aspect-video', 'h-auto', 'w-full', 'object-cover', 'md:block']}
      />

      <figcaption class={['text-center', 'md:bg-foreground', 'md:p-6']}>
        <p class={['text-sm', 'font-medium', 'text-primary-foreground', 'md:text-base']}>
          BETA READERS NEEDED
        </p>
      </figcaption>
    </figure>
  </div>
</section>
