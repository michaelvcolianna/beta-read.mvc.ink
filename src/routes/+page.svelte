<script>
  import './layout.css';
  import BookInfo from '$lib/components/BookInfo.svelte';
  import ContentWarning from '$lib/components/ContentWarning.svelte';
  import FieldLabel from '$lib/components/FieldLabel.svelte';
  import IconChevronDown from '$lib/components/Icons/ChevronDown.svelte';
  import IconCircleCheckBig from '$lib/components/Icons/CircleCheckBig.svelte';
  import IconSendHorizontal from '$lib/components/Icons/SendHorizontal.svelte';
  import RadioInput from '$lib/components/RadioInput.svelte';
  import RequiredStar from '$lib/components/RequiredStar.svelte';
  import SocialLink from '$lib/components/SocialLink.svelte';
  import TextInput from '$lib/components/TextInput.svelte';
  import CircleCheckBig from '$lib/components/Icons/CircleCheckBig.svelte';

  let checked = $state('');
  let submitted = $state(false);
</script>

<main class="min-h-screen bg-background">
  <section class="relative w-full overflow-hidden hero-gradient">
    <!-- @todo Canvas with animation as bg -->
    <div class="relative section-container py-8 md:py-16">
      <figure>
        <!-- @todo Hide image on mobile, only show figcaption & bg -->
        <img
          src="https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/"
          alt="Illustration by Jaroslaw Marcinek"
          class="hidden aspect-video h-auto w-full object-cover md:block"
        />

        <figcaption>
          <p>BETA READERS NEEDED</p>
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
            huge fight. Everyone has a limit, and the stress is causing them to take it out on one
            another – as well as on themselves. Defeating the Gaians will bring them both to the
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

          <!-- @todo Netlify formify -->
          <form class="space-y-6">
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

              <input type="hidden" id="delivery" value={checked} />
            </div>

            <div class="space-y-2">
              <FieldLabel forId="about">What made you want to read?</FieldLabel>

              <textarea
                id="about"
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
      <div>
        <h2>Praise &amp: Reactions</h2>

        <p>
          Some things others readers have said about their beta read, or about MVC’s first book, <a
            href="/">Fractured Children or Earth</a
          >.
        </p>
      </div>

      <div>
        <!-- @todo Make these a component -->
        <article>
          <!-- @todo Quote icon -->
          <blockquote>
            When I tell you that I cried my eyes out, please know that very few books have ever done
            that. I’ve got a very high tolerance for grief and sadness. Your story will haunt me for
            months, and I can't wait to see it published.
          </blockquote>

          <footer>
            <div>
              <cite
                ><a href="https://bsky.app/profile/juliebihn.bsky.social">@juliebihn.bsky.social</a
                >, author of <em>Titanic Voyage</em></cite
              >

              <p>For <em>Fragile Gamete of Resistance</em></p>
            </div>
          </footer>
        </article>

        <article>
          <!-- @todo Quote icon -->

          <blockquote>
            Holy crap, man. Are you okay? Because that ending really worries me. I mean... it’s
            phenomenal. But you should see a therapist.
          </blockquote>

          <footer>
            <div>
              <cite>bookish_nova (Discord), reader</cite>

              <p>For <em>Fragile Gamete of Resistance</em></p>
            </div>
          </footer>
        </article>

        <article>
          <!-- @todo Quote icon -->

          <blockquote>
            You’re a very good writer, but this was way too woke for me to read.
          </blockquote>

          <footer>
            <div>
              <cite>Creigh Maxfield, reader</cite>

              <p>For <em>Fractured Children of Earth</em></p>
            </div>
          </footer>
        </article>

        <article>
          <!-- @todo Quote icon -->

          <blockquote>
            MVC writes with the wonder of Chambers and the heart of Le Guin. This is science fiction
            at its finest.
          </blockquote>

          <footer>
            <div>
              <cite
                ><a href="https://kadoore.com/">K.A. Doore</a>, author of
                <em>The Chronicles of Ghadid</em> trilogy</cite
              >

              <p>For <em>Fractured Children of Earth</em></p>
            </div>
          </footer>
        </article>
      </div>
    </div>
  </section>

  <section class="w-full py-12 md:py-20">
    <div class="section-container">
      <div>
        <div>
          <div>
            <h2>Sample</h2>

            <p>From Chapter Four, <em>Every Tear That Softly Stains</em></p>
          </div>
        </div>

        <div>
          <!-- @todo Expanded/contracted states -->
          <article>
            <p>
              This discussion suddenly reminded Davi of the coffee contract fight that made the five
              members of the Vinillense quit. As well, it drew some similarity to his argument with
              Mary where she almost hit him. Anger clouded his judgment both times, and though
              Puccar’s stubborn refusal to help burned him like a grenade bolt, he somehow wrangled
              his emotions.
            </p>

            <p>
              “Just so I understand: You yourself said that his plan is to take us over and absorb
              our culture, and that you don’t want that. You agree that Ganmel needs to be stopped.
              But instead of taking direct action against him, you’re willing to wait and see if you
              can legislate him away? Do I have that right?” Davi asked, barely keeping himself
              under control.
            </p>

            <p>
              Puccar waved his hand in dismissal, then signed back, “I understand that you think
              this is more urgent than it really is, but I think you’re overreacting. We have plenty
              of time to stop him the right way.”
            </p>

            <p>
              Mary clenched her fists in response to that and Davi put his hand on her back in
              support. To Puccar, he said, “We have a device that blocks dielsis. It blocks the
              power and alerts us of the attempt. The Cartel has already held several meetings with
              some cities, using those devices. We’ve made no headway. Nobody believes us. Yet we
              are at the nine year mark that Ganmel set for the final stage of his plan. So forgive
              us when we say it’s pretty fucking urgent.”
            </p>

            <p>This didn’t sway Puccar. “And I’m telling you we will handle him.”</p>
          </article>

          <!-- @todo Gradient overlay when contracted -->
        </div>

        <div>
          <button type="button">
            <!-- @todo Different text for state -->
            <span>Show Less/Continue Reading</span>

            <!-- @todo Chevron icon, rotate for state -->
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
            communicate directly with you about this book. Your data is never saved to any
            third-party database, sold, shared, or used for marketing purposes.
          </p>

          <p>
            Once you complete your beta read, your information will be deleted, unless otherwise
            specified by you. By submitting the form, you consent to receiving direct communication
            from MVC regarding your advance reader copy request.
          </p>
        </div>

        <div class="mt-8 border-t border-border pt-6 text-xs text-muted-foreground">
          <p>© 2026 MVC. All rights reserved.</p>
        </div>
      </div>
    </div>
  </footer>
</main>
