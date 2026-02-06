<script>
  import ContentWarning from '$lib/components/ContentWarning.svelte';
  import IconChevronDown from '$lib/components/Icons/ChevronDown.svelte';
</script>

<section class={['w-full', 'bg-card', 'py-12', 'md:py-16']}>
  <div class={['section-container']}>
    <div class={['mx-auto', 'max-w-2xl']}>
      <div
        class={[
          'prose',
          'prose-lg',
          'mb-10',
          'space-y-6',
          'text-foreground',
          '*:text-lg',
          '*:leading-relaxed'
        ]}
      >
        <p>
          If you’d asked Mary and Davi how things were going a month ago, it would have been rave
          reviews. Co-captains of a smuggling ship, they’d stumbled upon a universe-wide conspiracy
          – but they convinced their friends to fight back. Even though they lost a bunch of money,
          got robbed, and compromised their morals a little, things were back on track. Finally,
          they could start their first IVF cycle and maybe take a break, right? <em>Not so fast…</em
          >
        </p>

        <p>
          Despite a good start, Mary and Davi’s IVF cycle failed. On top of that, their friends are
          struggling to fight the Gaians. Those are the human-appearing aliens behind the plot to
          take over the Three Empires and oppress humanity. They seem to have already adjusted and
          are always several steps ahead. So Mary and Davi will have to put their dreams on hold <em
            >once again</em
          > to help out.
        </p>

        <p>
          But there seems to be no end to the bad news. Mary and Davi keep getting hit while they
          are down. Nobody else wants to stand up and fight back. And that’s before they have a huge
          argument. Everyone has a limit, and the stress is causing them to take it out on one
          another – as well as on themselves. Defeating the Gaians will bring them both to the
          breaking point, <strong>and neither is confident they’ll hold strong</strong>.
        </p>
      </div>

      <details class={['group', 'overflow-hidden', 'rounded-lg', 'bg-muted/50']}>
        <summary
          class={[
            'flex',
            'cursor-pointer',
            'items-center',
            'justify-between',
            'px-5',
            'py-4',
            'font-medium',
            'text-foreground',
            'transition-colors',
            'hover:bg-muted'
          ]}
        >
          <span class={['text-sm', 'tracking-wider', 'uppercase']}>Content Warnings</span>

          <IconChevronDown
            class={[
              'h-5',
              'w-5',
              'text-muted-foreground',
              'transition-transform',
              'group-open:rotate-180'
            ]}
          />
        </summary>

        <div class={['px-5', 'pb-5', 'text-sm', 'text-muted-foreground']}>
          <ul class={['space-y-2']}>
            <ContentWarning>Fertility difficulties</ContentWarning>

            <ContentWarning>Suicidal ideation and mentions</ContentWarning>

            <ContentWarning>Mentions of miscarriage</ContentWarning>

            <ContentWarning>Mentions of attempted sexual assault</ContentWarning>

            <ContentWarning>Violence, death, alcohol use, and language</ContentWarning>
          </ul>

          <p class={['mt-2']}>More detail is in the manuscript</p>
        </div>
      </details>
    </div>
  </div>
</section>
