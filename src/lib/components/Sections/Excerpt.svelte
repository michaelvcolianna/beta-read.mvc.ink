<script>
  import IconChevronDown from '$lib/components/Icons/ChevronDown.svelte';

  let expanded = $state(false);
</script>

<section class={['w-full', 'py-12', 'md:py-20']}>
  <div class={['section-container']}>
    <div class={['mx-auto', 'max-w-2xl']}>
      <div class={['mb-6', 'flex', 'items-center', 'gap-3']}>
        <div>
          <h2
            class={['font-display', 'text-2xl', 'font-semibold', 'text-foreground', 'md:text-3xl']}
          >
            Excerpt
          </h2>

          <p class={['text-sm', 'text-muted-foreground']}>From the introduction</p>
        </div>
      </div>

      <div class={['relative']}>
        <article
          class={[
            'prose',
            'prose-lg',
            'space-y-4',
            'overflow-hidden',
            'text-foreground/90',
            'transition-all',
            'duration-500',
            expanded && 'max-h-850 md:max-h-680 lg:max-h-510',
            !expanded && 'max-h-64'
          ]}
        >
          <p
            class={[
              'first-letter:float-left',
              'first-letter:mt-1',
              'first-letter:mr-3',
              'first-letter:font-display',
              'first-letter:text-5xl',
              'first-letter:font-bold',
              'first-letter:text-primary'
            ]}
          >
            Artificial rain streaked across the window of the doctor’s office. It fell from special
            faucets in the sky dome, which projected the appearance of storm clouds to sell the
            illusion. Davi observed several birds dancing across the grass outside, pecking at
            worms. His reflection looked back at him, and he briefly glanced at the stubble on his
            head, his untidy beard, and the scar from a burn on his cheek.
          </p>

          <p>
            Next to Davi, his partner and co-captain, Mary, rubbed her lower back. She wore her
            usual red coat and had her black hair in a bun. Whether she realized it or not, she
            grumbled slightly, then she typed something on her wrist computer.
          </p>

          <p>
            The circlet on Davi’s head came to life with a puff of mist, projecting his
            heads-up-display (or, hud, for short). A box popped up on the right side of the screen
            with Mary’s message.
          </p>

          <p>[I really hope we won’t have to do any more injections,] her chat read.</p>

          <p>Davi replied with an exaggerated sign for, “Me too.”</p>

          <p>
            Mary’s message referred to progesterone in oil. Each night for the past several weeks,
            Davi had administered it with an intramuscular injection. The needle itself meant
            business, and despite massaging around the area as recommended, the oil built up. It
            wasn’t comfortable.
          </p>

          <p>
            Their fertility specialist, Doctor Svakino, entered the room. Her presence unnerved
            Davi, even though she’d been with them through the entirety of the cycle. This was
            because of a small pin on the lapel of her coat: A red base, with a golden sunburst and
            golden highlights.
          </p>

          <p>
            Over the course of the past few months, Davi and Mary had learned that pin indicated
            support for a fascist shadow government. The plot sounded like something out of a novel
            or a film: Gaians, a group of human-appearing aliens, had already taken control of
            several planets in the Three Empires.
          </p>

          <p>
            In the process of uncovering that information, Davi and Mary had violated their
            commitments to non-violence, lost their savings, and almost rendered their smuggling
            group defunct.
          </p>

          <p>
            They’d somehow made it through intact and plans were in motion as a result of their
            efforts. The organization they worked for, the Cartel, voted to alert humanity of the
            threat because of their hard work and evidence. While Davi and Mary went through IVF on
            Ghestra, Cartel smuggling groups were meeting with planetary governments of the Three
            Empires to urge action.
          </p>

          <p>
            Oh – and some of those aliens had the ability to control minds. So yeah, the seemingly
            innocuous pin put Davi on edge a little.
          </p>

          <p>
            They’d been on Ghestra for nearly a month, after all kinds of <em>other</em> injections to
            produce a clutch of eggs. The progesterone shots were a necessary measure to make sure Mary’s
            body would be ready for an IVF procedure. It was the latest entry in their fertility journey:
            trying on their own for a year, two IUI attempts, a chemical pregnancy, and an outright failure.
          </p>

          <p>
            This time they’d gotten seventeen eggs from Mary, but her hormone levels still weren’t
            right. So they would have to freeze the fertilized eggs. Once her next cycle came
            around, they would thaw an embryo and transfer it.
          </p>

          <p>“Mary, Davi. Good to see you again,” the doctor signed.</p>

          <p>Mary signed back, “Hello, Doctor.”</p>

          <p>
            Doctor Svakino took a seat opposite them. She brushed her long, blonde hair behind her,
            then operated her wrist computer. The table between them lit up with some information.
          </p>

          <p>“Mary, today’s bloodwork results,” the doctor signed.</p>

          <p>
            Mary pursed her lips and narrowed her eyes. Davi knew the look well, especially of late.
            Anger. There had been so many setbacks to starting the IVF process, and while they
            already knew about the latest delay, it clearly grated on her.
          </p>

          <p>
            “Can we stop the injections, at least?” Davi signed. Better for him to take action, as
            it might defuse some of Mary’s frustration.
          </p>

          <p>Doctor Svakino gently nodded. “Yes.”</p>

          <p>“And we can’t just go ahead with the transfer anyway?” Davi asked.</p>

          <p>
            “Even if we could do the transfer now, we’d be taking an already low chance of success
            and cutting it in half. With her current progesterone level, Mary would have a small
            percentage of an embryo attaching,” Doctor Svakino signed in reply.
          </p>

          <p>
            Davi clenched his fists and breathed slowly through his nose. If she wasn’t already
            doing so, Mary would blame herself for this.
          </p>

          <p>
            He wanted to press the doctor further, but Mary reached over and grasped his hand to
            quell further argument. While events had introduced some tension between the two of them
            lately, they still had a solid foundation. They’d built it on love and he understood to
            trust her on this.
          </p>

          <p>“That makes sense. We will wait,” Mary signed to the doctor.</p>

          <p>
            Davi stared into her eyes, which were ringed by upcoming tears, but he caught a slightly
            imperceptible twitch of her nostril. <em>Don’t worry, it’ll work out</em>, it said.
          </p>
        </article>

        {#if !expanded}
          <div
            class={[
              'pointer-events-none',
              'absolute',
              'right-0',
              'bottom-0',
              'left-0',
              'h-32',
              'bg-linear-to-t',
              'from-background',
              'to-transparent'
            ]}
          ></div>
        {/if}
      </div>

      <div class={['mt-6', 'text-center']}>
        <button
          type="button"
          onclick={() => (expanded = !expanded)}
          class={[
            'group',
            'inline-flex',
            'h-10',
            'items-center',
            'justify-center',
            'gap-2',
            'rounded-md',
            'border',
            'border-input',
            'bg-background',
            'px-4',
            'py-2',
            'text-sm',
            'font-medium',
            'whitespace-nowrap',
            'ring-offset-background',
            'transition-colors',
            'hover:bg-accent',
            'hover:text-accent-foreground',
            'focus-visible:ring-2',
            'focus-visible:ring-ring',
            'focus-visible:ring-offset-2',
            'focus-visible:outline-hidden',
            'disabled:pointer-events-none',
            'disabled:opacity-50',
            '[&_svg]:pointer-events-none',
            '[&_svg]:size-4',
            '[&_svg]:shrink-0'
          ]}
        >
          <span>{expanded ? 'Show Less' : 'Continue Reading'}</span>

          <IconChevronDown
            class={[
              'ml-2',
              'h-4',
              'w-4',
              'transition-transform',
              'duration-300',
              expanded && 'rotate-180'
            ]}
          />
        </button>
      </div>
    </div>
  </div>
</section>
