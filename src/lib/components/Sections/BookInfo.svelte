<script>
  import BookInfo from '$lib/components/BookInfo.svelte';
  import IconBookOpen from '$lib/components/Icons/BookOpen.svelte';
  import IconCalendarDays from '$lib/components/Icons/CalendarDays.svelte';
  import IconClock from '$lib/components/Icons/Clock.svelte';
  import IconFolderOpen from '$lib/components/Icons/FolderOpen.svelte';
</script>

<section class={['w-full', 'py-12', 'md:py-20']}>
  <div class={['section-container', 'text-center']}>
    <h1
      class={[
        'mb-4',
        'text-gradient',
        'font-display',
        'text-4xl',
        'font-bold',
        'tracking-tight',
        'sm:text-5xl',
        'md:text-6xl',
        'lg:text-7xl'
      ]}
    >
      <span>Fragile Gamete</span>
      <br />
      <span>of Resistance</span>
    </h1>

    <p
      class={['mb-8', 'text-lg', 'font-medium', 'text-muted-foreground', 'md:mb-12', 'md:text-xl']}
    >
      by <span class={['text-foreground']}>Michael V. Colianna</span> (he/xe)
    </p>

    <div class={['flex', 'flex-wrap', 'justify-center', 'gap-4', 'md:gap-8']}>
      <BookInfo green help="Genre" label="Adult Sci-Fi" Icon={IconFolderOpen} />

      <BookInfo red help="Word Count" label="110k words" Icon={IconBookOpen} />

      <BookInfo green help="Reading Time" label="~9 hours" Icon={IconClock} />

      <BookInfo red help="Timeline" label="End of March" Icon={IconCalendarDays} />
    </div>
  </div>
</section>
