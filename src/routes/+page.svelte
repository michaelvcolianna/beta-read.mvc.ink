<script>
  import './layout.css';
  import BookInfo from '$lib/components/BookInfo.svelte';
  import ContentWarning from '$lib/components/ContentWarning.svelte';
  import FieldLabel from '$lib/components/FieldLabel.svelte';
  import HeroBackground from '$lib/components/HeroBackground.svelte';
  import IconChevronDown from '$lib/components/Icons/ChevronDown.svelte';
  import IconCircleCheckBig from '$lib/components/Icons/CircleCheckBig.svelte';
  import IconSendHorizontal from '$lib/components/Icons/SendHorizontal.svelte';
  import RadioInput from '$lib/components/RadioInput.svelte';
  import RequiredStar from '$lib/components/RequiredStar.svelte';
  import SocialLink from '$lib/components/SocialLink.svelte';
  import Testimonial from '$lib/components/Testimonial.svelte';
  import TextInput from '$lib/components/TextInput.svelte';

  const netlifyFormName = 'BetaReaders';

  let checked = $state('gdocs');
  let expanded = $state(false);
  let submitted = $state(false);

  const handleSubmit = (event) => {
    event.preventDefault();

    const form = event.target;
    const formData = new FormData(form);

    fetch('/', {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: new URLSearchParams(formData).toString()
    })
      .then(() => (submitted = true))
      .catch((error) => console.log('form submit error:', error));
  };

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

<main class="min-h-screen bg-background">
  <section class="relative w-full overflow-hidden bg-card-foreground">
    <HeroBackground />

    <div class="relative section-container py-8 md:py-16">
      <figure class="relative overflow-hidden rounded-lg md:rounded-2xl">
        <img
          sizes="(max-width: 824px) 100vw, 824px"
          srcset="
            https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/200x0 200w,
            https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/498x0 498w,
            https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/698x0 698w,
            https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/824x0 824w"
          src="https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/824x0"
          alt="Illustration by Jaroslaw Marcinek"
          fetchpriority="high"
          height="458"
          width="824"
          class="hidden aspect-video h-auto w-full object-cover md:block"
        />

        <figcaption class="text-center md:bg-foreground md:p-6">
          <p class="text-sm font-medium text-primary-foreground md:text-base">
            BETA READERS NEEDED
          </p>
        </figcaption>
      </figure>
    </div>
  </section>

  <section class="w-full py-12 md:py-20">
    <div class="section-container text-center">
      <h1
        class="mb-4 text-gradient font-display text-4xl font-bold tracking-tight sm:text-5xl md:text-6xl lg:text-7xl"
      >
        <span>Fragile Gamete</span>
        <br />
        <span>of Resistance</span>
      </h1>

      <p class="mb-8 text-lg font-medium text-muted-foreground md:mb-12 md:text-xl">
        by <span class="text-foreground">Michael V. Colianna</span> (he/xe)
      </p>

      <div class="flex flex-wrap justify-center gap-4 md:gap-8">
        <BookInfo green help="Genre" label="Adult Sci-Fi" icon="folder-open" />

        <BookInfo red help="Word Count" label="110k words" icon="book-open" />

        <BookInfo green help="Reading Time" label="~9 hours" icon="clock" />

        <BookInfo red help="Timeline" label="End of March" icon="calendar-days" />
      </div>
    </div>
  </section>

  <section class="w-full bg-card py-12 md:py-16">
    <div class="section-container">
      <div class="mx-auto max-w-2xl">
        <div class="prose prose-lg mb-10 space-y-6 text-foreground *:text-lg *:leading-relaxed">
          <p>
            If you’d asked Mary and Davi how things were going a month ago, it would have been rave
            reviews. Co-captains of a smuggling ship, they’d stumbled upon a universe-wide
            conspiracy – but they convinced their friends to fight back. Even though they lost a
            bunch of money, got robbed, and compromised their morals a little, things were back on
            track. Finally, they could start their first IVF cycle and maybe take a break, right? <em
              >Not so fast…</em
            >
          </p>

          <p>
            Despite a good start, Mary and Davi’s IVF cycle failed. On top of that, their friends
            are struggling to fight the Gaians. Those are the human-appearing aliens behind the plot
            to take over the Three Empires and oppress humanity. They seem to have already adjusted
            and are always several steps ahead. So Mary and Davi will have to put their dreams on
            hold <em>once again</em> to help out.
          </p>

          <p>
            But there seems to be no end to the bad news. Mary and Davi keep getting hit while they
            are down. Nobody else wants to stand up and fight back. And that’s before they have a
            huge argument. Everyone has a limit, and the stress is causing them to take it out on
            one another – as well as on themselves. Defeating the Gaians will bring them both to the
            breaking point, <strong>and neither is confident they’ll hold strong</strong>.
          </p>
        </div>

        <details class="group overflow-hidden rounded-lg bg-muted/50">
          <summary
            class="flex cursor-pointer items-center justify-between px-5 py-4 font-medium text-foreground transition-colors hover:bg-muted"
          >
            <span class="text-sm tracking-wider uppercase">Content Warnings</span>

            <IconChevronDown
              class="h-5 w-5 text-muted-foreground transition-transform group-open:rotate-180"
            />
          </summary>

          <div class="px-5 pb-5 text-sm text-muted-foreground">
            <ul class="space-y-2">
              <ContentWarning>Fertility difficulties</ContentWarning>

              <ContentWarning>Suicidal ideation and mentions</ContentWarning>

              <ContentWarning>Mentions of miscarriage</ContentWarning>

              <ContentWarning>Mentions of attempted sexual assault</ContentWarning>

              <ContentWarning>Violence, death, alcohol use, and language</ContentWarning>
            </ul>

            <p class="mt-2">More detail is in the manuscript</p>
          </div>
        </details>
      </div>
    </div>
  </section>

  <section class="w-full py-12 md:py-16">
    <div class="section-container text-center">
      <h2 class="mb-3 font-display text-2xl font-semibold text-foreground md:text-3xl">
        Connect with MVC
      </h2>

      <p class="mb-8 text-muted-foreground">Get in contact to read, or use the form below.</p>

      <div class="flex flex-wrap justify-center gap-4">
        <SocialLink
          help="Connect on Bluesky"
          href="https://bsky.app/profile/mvc.ink"
          icon="bluesky"
          label="Bluesky"
        />

        <SocialLink
          help="Connect on Discord"
          href="http://discord.com/users/740751379571933265"
          icon="discord"
          label="Discord"
        />

        <SocialLink
          help="Visit MVC's Website"
          href="https://mvc.ink"
          icon="globe"
          label="Website"
        />

        <SocialLink help="Send MVC an Email" href="mailto:info@mvc.ink" icon="mail" label="Email" />
      </div>
    </div>
  </section>

  <section class="w-full bg-card py-12 md:py-20">
    <div class="section-container">
      {#if submitted}
        <div class="mx-auto max-w-md py-12 text-center">
          <div
            class="mb-6 inline-flex h-16 w-16 items-center justify-center rounded-full bg-highlight/20"
          >
            <IconCircleCheckBig class="h-8 w-8 text-highlight" />
          </div>

          <h2 class="mb-3 font-display text-2xl font-semibold text-foreground">
            Submission Received!
          </h2>

          <p class="text-muted-foreground">Thank you! MVC will be in touch soon!</p>
        </div>
      {:else}
        <div class="mx-auto max-w-md">
          <div class="mb-10 text-center">
            <h2 class="mb-3 font-display text-2xl font-semibold text-foreground md:text-3xl">
              Sign up to Beta Read
            </h2>

            <p class="text-muted-foreground">
              Interested in being a beta reader but unable to connect via the options above? Fill
              out the following form.
            </p>
          </div>

          <form
            netlify-honeypot="favorite-cat"
            data-netlify="true"
            name={netlifyFormName}
            method="post"
            onsubmit={handleSubmit}
            class="space-y-6"
          >
            <p class="hidden">
              <label>
                What's your favorite cat?
                <input name="favorite-cat" type="text" />
              </label>
            </p>

            <TextInput label="Name" id="name" type="text" placeholder="Your name" required />

            <TextInput
              label="Email"
              id="email"
              type="email"
              placeholder="you@example.com"
              required
            />

            <TextInput
              label="Pronouns"
              id="pronouns"
              type="text"
              placeholder="e.g., she/her, they/them (Optional)"
            />

            <div class="space-y-3">
              <div
                class="text-sm leading-none font-medium peer-disabled:cursor-not-allowed peer-disabled:opacity-70"
              >
                Preferred Way To Read &amp; Comment <RequiredStar />
              </div>

              <div role="radiogroup" aria-required="true" class="flex flex-col gap-3">
                <RadioInput value="gdocs" label="Google Docs" bind:checked />

                <RadioInput value="pdf" label="PDF" bind:checked />

                <RadioInput value="word" label="Word Doc" bind:checked />

                <RadioInput value="other" label="Other (specify in field below)" bind:checked />
              </div>

              <input type="hidden" name="delivery" value={checked} />
            </div>

            <div class="space-y-2">
              <FieldLabel forId="about">What made you want to read?</FieldLabel>

              <textarea
                id="about"
                name="about"
                placeholder="Are you a reviewer, blogger, or just a sci-fi enthusiast? Tell me a bit about yourself! (Optional)"
                rows="4"
                class="flex min-h-20 w-full resize-none rounded-md border border-input bg-background px-3 py-2 text-sm ring-offset-background placeholder:text-muted-foreground focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 focus-visible:outline-hidden disabled:cursor-not-allowed disabled:opacity-50"
              ></textarea>
            </div>

            <p class="text-center text-sm">
              <a href="#privacy" class="text-primary transition-colors hover:underline"
                >Concerned about privacy?</a
              >
            </p>

            <input type="hidden" name="form-name" value={netlifyFormName} />

            <button
              type="submit"
              class="inline-flex h-10 w-full items-center justify-center gap-2 rounded-md bg-primary px-4 py-6 text-sm font-medium whitespace-nowrap text-primary-foreground ring-offset-background transition-colors hover:bg-primary/90 focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 focus-visible:outline-hidden disabled:pointer-events-none disabled:opacity-50 [&_svg]:pointer-events-none [&_svg]:size-4 [&_svg]:shrink-0"
            >
              <IconSendHorizontal class="mr-2 h-4 w-4" />
              Submit Request
            </button>
          </form>
        </div>
      {/if}
    </div>
  </section>

  <section class="w-full bg-card py-12 md:py-20">
    <div class="section-container">
      <div class="mb-10 text-center md:mb-14">
        <h2 class="mb-3 font-display text-2xl font-semibold text-foreground md:text-3xl">
          Praise &amp; Reactions
        </h2>

        <p class="text-muted-foreground">
          Some things readers have said about their beta read, or about MVC’s first book, <a
            href="https://bookshop.org/p/books/fractured-children-of-earth-michael-v-colianna/187fde3f7ab8190f"
            class="font-medium underline">Fractured Children of Earth</a
          >.
        </p>
      </div>

      <div class="grid grid-cols-1 gap-6 md:grid-cols-2">
        <Testimonial>
          {#snippet quote()}
            You’re a very good writer, but this was way too woke for me to read.
          {/snippet}

          {#snippet author()}
            Creigh Maxfield, reader
          {/snippet}

          {#snippet role()}
            For <em>Fractured Children of Earth</em>
          {/snippet}
        </Testimonial>

        <Testimonial>
          {#snippet quote()}
            Holy crap, man. Are you okay? Because that ending really worries me. I mean... it’s
            phenomenal. But you should see a therapist.
          {/snippet}

          {#snippet author()}
            bookish_nova (Discord), reader
          {/snippet}

          {#snippet role()}
            For <em>Fragile Gamete of Resistance</em>
          {/snippet}
        </Testimonial>

        <Testimonial>
          {#snippet quote()}
            OK... I need the follow up to this like right now. You can't leave me hanging like that!
          {/snippet}

          {#snippet author()}
            PinkCupcake (Discord), reader
          {/snippet}

          {#snippet role()}
            For <em>Fragile Gamete of Resistance</em>
          {/snippet}
        </Testimonial>

        <Testimonial>
          {#snippet quote()}
            For a first draft, I really appreciate the care you took with the words. I read a lot of
            drafts where the author throws in ableist language without realizing it, so it was a
            nice refresher to see multiple disabled characters who don't need to be fixed.
          {/snippet}

          {#snippet author()}
            Klara (Discord), reader
          {/snippet}

          {#snippet role()}
            For <em>Fragile Gamete of Resistance</em>
          {/snippet}
        </Testimonial>
      </div>
    </div>
  </section>

  <section class="w-full py-12 md:py-20">
    <div class="section-container">
      <div class="mx-auto max-w-2xl">
        <div class="mb-6 flex items-center gap-3">
          <div>
            <h2 class="font-display text-2xl font-semibold text-foreground md:text-3xl">Excerpt</h2>

            <p class="text-sm text-muted-foreground">From the introduction</p>
          </div>
        </div>

        <div class="relative">
          <article
            class={[
              'prose prose-lg space-y-4 overflow-hidden text-foreground/90 transition-all duration-500',
              expanded && 'max-h-850 md:max-h-680 lg:max-h-510',
              !expanded && 'max-h-64'
            ]}
          >
            <p
              class="first-letter:float-left first-letter:mt-1 first-letter:mr-3 first-letter:font-display first-letter:text-5xl first-letter:font-bold first-letter:text-primary"
            >
              Artificial rain streaked across the window of the doctor’s office. It fell from
              special faucets in the sky dome, which projected the appearance of storm clouds to
              sell the illusion. Davi observed several birds dancing across the grass outside,
              pecking at worms. His reflection looked back at him, and he briefly glanced at the
              stubble on his head, his untidy beard, and the scar from a burn on his cheek.
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
              because of a small pin on the lapel of her coat: A red base, with a golden sunburst
              and golden highlights.
            </p>

            <p>
              Over the course of the past few months, Davi and Mary had learned that pin indicated
              support for a fascist shadow government. The plot sounded like something out of a
              novel or a film: Gaians, a group of human-appearing aliens, had already taken control
              of several planets in the Three Empires.
            </p>

            <p>
              In the process of uncovering that information, Davi and Mary had violated their
              commitments to non-violence, lost their savings, and almost rendered their smuggling
              group defunct.
            </p>

            <p>
              They’d somehow made it through intact and plans were in motion as a result of their
              efforts. The organization they worked for, the Cartel, voted to alert humanity of the
              threat because of their hard work and evidence. While Davi and Mary went through IVF
              on Ghestra, Cartel smuggling groups were meeting with planetary governments of the
              Three Empires to urge action.
            </p>

            <p>
              Oh – and some of those aliens had the ability to control minds. So yeah, the seemingly
              innocuous pin put Davi on edge a little.
            </p>

            <p>
              They’d been on Ghestra for nearly a month, after all kinds of <em>other</em> injections
              to produce a clutch of eggs. The progesterone shots were a necessary measure to make sure
              Mary’s body would be ready for an IVF procedure. It was the latest entry in their fertility
              journey: trying on their own for a year, two IUI attempts, a chemical pregnancy, and an
              outright failure.
            </p>

            <p>
              This time they’d gotten seventeen eggs from Mary, but her hormone levels still weren’t
              right. So they would have to freeze the fertilized eggs. Once her next cycle came
              around, they would thaw an embryo and transfer it.
            </p>

            <p>“Mary, Davi. Good to see you again,” the doctor signed.</p>

            <p>Mary signed back, “Hello, Doctor.”</p>

            <p>
              Doctor Svakino took a seat opposite them. She brushed her long, blonde hair behind
              her, then operated her wrist computer. The table between them lit up with some
              information.
            </p>

            <p>“Mary, today’s bloodwork results,” the doctor signed.</p>

            <p>
              Mary pursed her lips and narrowed her eyes. Davi knew the look well, especially of
              late. Anger. There had been so many setbacks to starting the IVF process, and while
              they already knew about the latest delay, it clearly grated on her.
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
              quell further argument. While events had introduced some tension between the two of
              them lately, they still had a solid foundation. They’d built it on love and he
              understood to trust her on this.
            </p>

            <p>“That makes sense. We will wait,” Mary signed to the doctor.</p>

            <p>
              Davi stared into her eyes, which were ringed by upcoming tears, but he caught a
              slightly imperceptible twitch of her nostril. <em>Don’t worry, it’ll work out</em>, it
              said.
            </p>
          </article>

          {#if !expanded}
            <div
              class="pointer-events-none absolute right-0 bottom-0 left-0 h-32 bg-linear-to-t from-background to-transparent"
            ></div>
          {/if}
        </div>

        <div class="mt-6 text-center">
          <button
            type="button"
            onclick={() => (expanded = !expanded)}
            class="group inline-flex h-10 items-center justify-center gap-2 rounded-md border border-input bg-background px-4 py-2 text-sm font-medium whitespace-nowrap ring-offset-background transition-colors hover:bg-accent hover:text-accent-foreground focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 focus-visible:outline-hidden disabled:pointer-events-none disabled:opacity-50 [&_svg]:pointer-events-none [&_svg]:size-4 [&_svg]:shrink-0"
          >
            <span>{expanded ? 'Show Less' : 'Continue Reading'}</span>

            <IconChevronDown
              class={['ml-2 h-4 w-4 transition-transform duration-300', expanded && 'rotate-180']}
            />
          </button>
        </div>
      </div>
    </div>
  </section>

  <footer id="privacy" class="w-full scroll-mt-8 bg-muted/30 py-10 md:py-16">
    <div class="section-container">
      <div class="mx-auto max-w-2xl text-center">
        <h3 class="mb-4 font-display text-lg font-semibold text-foreground">Privacy Policy</h3>

        <div class="space-y-3 text-sm text-muted-foreground">
          <p>
            Your privacy matters. Information submitted through this site is used solely by MVC to
            communicate directly with you about this book. Your data is never sold, shared, or used
            for marketing purposes.
          </p>

          <p>
            Once you complete your beta read, your information will be deleted, unless otherwise
            specified by you. By submitting the form, you consent to receiving direct communication
            from MVC regarding your beta reader copy request.
          </p>
        </div>

        <div class="mt-8 border-t border-border pt-6 text-xs text-muted-foreground">
          <p>
            © 2026 MVC. All rights reserved. <span class="hidden md:inline"
              >Header image by <a
                href="https://www.artstation.com/yaroslavus"
                class="font-medium underline">Jaroslaw Marcinek</a
              >.</span
            >
          </p>
        </div>
      </div>
    </div>
  </footer>
</main>
