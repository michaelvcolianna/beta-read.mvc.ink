<script>
  import IconQuote from '$lib/components/Icons/Quote.svelte';

  let { book, quote, reader } = $props();
</script>

<article
  class={['relative', 'rounded-xl', 'bg-background', 'p-6', 'transition-transform', 'duration-300']}
>
  <IconQuote class={['absolute', 'top-4', 'right-4', 'h-8', 'w-8', 'text-primary/20']} />

  <blockquote class={['mb-4', 'pr-8', 'leading-relaxed', 'text-foreground']}>
    {quote}
  </blockquote>

  <footer class={['flex', 'items-center', 'gap-3']}>
    <div>
      <cite class={['text-sm', 'font-medium', 'text-foreground', 'not-italic']}>
        {reader}, reader
      </cite>

      <p class={['text-xs', 'text-muted-foreground']}>For <em>{book}</em></p>
    </div>
  </footer>
</article>
