<script>
  import Link from '$lib/components/Link.svelte';
  import Testimonial from '$lib/components/Testimonial.svelte';
</script>

<section class={['w-full', 'bg-card', 'py-12', 'md:py-20']}>
  <div class={['section-container']}>
    <div class={['mb-10', 'text-center', 'md:mb-14']}>
      <h2
        class={[
          'mb-3',
          'font-display',
          'text-2xl',
          'font-semibold',
          'text-foreground',
          'md:text-3xl'
        ]}
      >
        Praise &amp; Reactions
      </h2>

      <p class={['text-muted-foreground']}>
        Some things readers have said about their beta read, or about MVC’s first book, <Link
          href="https://bookshop.org/p/books/fractured-children-of-earth-michael-v-colianna/187fde3f7ab8190f"
          >Fractured Children of Earth</Link
        >.
      </p>
    </div>

    <div class={['grid', 'grid-cols-1', 'gap-6', 'md:grid-cols-2']}>
      <Testimonial
        book="Fractured Children of Earth"
        reader="Creigh Maxfield"
        quote="You’re a very good writer, but this was way too woke for me to read."
      />

      <Testimonial
        book="Fragile Gamete of Resistance"
        reader="bookish_nova (Discord)"
        quote="Holy crap, man. Are you okay? Because that ending really worries me. I mean... it’s phenomenal. But you should see a therapist."
      />

      <Testimonial
        book="Fragile Gamete of Resistance"
        reader="PinkCupcake (Discord)"
        quote="OK... I need the follow up to this like right now. You can't leave me hanging like that!"
      />

      <Testimonial
        book="Fragile Gamete of Resistance"
        reader="Klara (Discord)"
        quote="For a first draft, I really appreciate the care you took with the words. I read a lot of drafts where the author throws in ableist language without realizing it, so it was a nice refresher to see multiple disabled characters who don't need to be fixed."
      />
    </div>
  </div>
</section>
