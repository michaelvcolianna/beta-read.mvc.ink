<script>
  import FieldLabel from '$lib/components/FieldLabel.svelte';
  import IconCircleAlert from '$lib/components/Icons/CircleAlert.svelte';
  import IconCircleCheckBig from '$lib/components/Icons/CircleCheckBig.svelte';
  import IconSendHorizontal from '$lib/components/Icons/SendHorizontal.svelte';
  import RadioInput from '$lib/components/RadioInput.svelte';
  import RequiredStar from '$lib/components/RequiredStar.svelte';
  import TextInput from '$lib/components/TextInput.svelte';

  const netlifyFormName = 'BetaReaders';

  let checked = $state('gdocs');
  let error = $state(false);
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
      .catch(() => (error = true));
  };
</script>

<section class={['w-full', 'bg-card', 'py-12', 'md:py-20']}>
  <div class={['section-container']}>
    {#if error || submitted}
      {@const ResultIcon = error ? IconCircleAlert : IconCircleCheckBig}

      <div class={['mx-auto', 'max-w-md', 'py-12', 'text-center']}>
        <div
          class={[
            'mb-6',
            'inline-flex',
            'h-16',
            'w-16',
            'items-center',
            'justify-center',
            'rounded-full',
            error && 'bg-destructive/20',
            submitted && 'bg-highlight/20'
          ]}
        >
          <ResultIcon
            class={['h-8', 'w-8', error && 'text-accent', submitted && 'text-highlight']}
          />
        </div>

        <h2 class={['mb-3', 'font-display', 'text-2xl', 'font-semibold', 'text-foreground']}>
          {error ? 'Submission Issue' : 'Submission Received!'}
        </h2>

        <p class={['text-muted-foreground']}>
          {error
            ? 'There was a problem saving your information, please try again later or use one of the methods linked above.'
            : 'Thank you! MVC will be in touch soon!'}
        </p>
      </div>
    {:else}
      <div class={['mx-auto', 'max-w-md']}>
        <div class={['mb-10', 'text-center']}>
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
            Sign up to Beta Read
          </h2>

          <p class={['text-muted-foreground']}>
            Interested in being a beta reader but unable to connect via the options above? Fill out
            the following form.
          </p>
        </div>

        <form
          netlify-honeypot="favorite-cat"
          data-netlify="true"
          name={netlifyFormName}
          method="post"
          onsubmit={handleSubmit}
          class={['space-y-6']}
        >
          <p class={['hidden']}>
            <label>
              What's your favorite cat?
              <input name="favorite-cat" type="text" />
            </label>
          </p>

          <TextInput label="Name" id="name" type="text" placeholder="Your name" required />

          <TextInput label="Email" id="email" type="email" placeholder="you@example.com" required />

          <TextInput
            label="Pronouns"
            id="pronouns"
            type="text"
            placeholder="e.g., she/her, they/them (Optional)"
          />

          <div class={['space-y-3']}>
            <div
              class={[
                'text-sm',
                'leading-none',
                'font-medium',
                'peer-disabled:cursor-not-allowed',
                'peer-disabled:opacity-70'
              ]}
            >
              Preferred Way To Read &amp; Comment <RequiredStar />
            </div>

            <div role="radiogroup" aria-required="true" class={['flex', 'flex-col', 'gap-3']}>
              <RadioInput value="gdocs" label="Google Docs" bind:checked />

              <RadioInput value="pdf" label="PDF" bind:checked />

              <RadioInput value="word" label="Word Doc" bind:checked />

              <RadioInput value="other" label="Other (specify in field below)" bind:checked />
            </div>

            <input type="hidden" name="delivery" value={checked} />
          </div>

          <div class={['space-y-2']}>
            <FieldLabel forId="about">What made you want to read?</FieldLabel>

            <textarea
              id="about"
              name="about"
              placeholder="Are you a reviewer, blogger, or just a sci-fi enthusiast? Tell me a bit about yourself! (Optional)"
              rows="4"
              class={[
                'flex',
                'min-h-20',
                'w-full',
                'resize-none',
                'rounded-md',
                'border',
                'border-input',
                'bg-background',
                'px-3',
                'py-2',
                'text-sm',
                'ring-offset-background',
                'placeholder:text-muted-foreground',
                'focus-visible:ring-2',
                'focus-visible:ring-ring',
                'focus-visible:ring-offset-2',
                'focus-visible:outline-hidden',
                'disabled:cursor-not-allowed',
                'disabled:opacity-50'
              ]}
            ></textarea>
          </div>

          <p class={['text-center', 'text-sm']}>
            <a href="#privacy" class={['text-primary', 'transition-colors', 'hover:underline']}
              >Concerned about privacy?</a
            >
          </p>

          <input type="hidden" name="form-name" value={netlifyFormName} />

          <button
            type="submit"
            class={[
              'inline-flex',
              'h-10',
              'w-full',
              'items-center',
              'justify-center',
              'gap-2',
              'rounded-md',
              'bg-primary',
              'px-4',
              'py-6',
              'text-sm',
              'font-medium',
              'whitespace-nowrap',
              'text-primary-foreground',
              'ring-offset-background',
              'transition-colors',
              'hover:bg-primary/90',
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
            <IconSendHorizontal class={['mr-2', 'h-4', 'w-4']} />
            Submit Request
          </button>
        </form>
      </div>
    {/if}
  </div>
</section>
