<script>
  import IconBluesky from '$lib/components/Icons/Bluesky.svelte';
  import IconDiscord from '$lib/components/Icons/Discord.svelte';
  import IconGlobe from '$lib/components/Icons/Globe.svelte';
  import IconMail from '$lib/components/Icons/Mail.svelte';
  import SocialLink from '$lib/components/SocialLink.svelte';
</script>

<section class={['w-full', 'py-12', 'md:py-16']}>
  <div class={['section-container', 'text-center']}>
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
      Connect with MVC
    </h2>

    <p class={['mb-8', 'text-muted-foreground']}>Get in contact to read, or use the form below.</p>

    <div class={['flex', 'flex-wrap', 'justify-center', 'gap-4']}>
      <SocialLink
        help="Connect on"
        href="https://bsky.app/profile/mvc.ink"
        Icon={IconBluesky}
        label="Bluesky"
      />

      <SocialLink
        help="Connect on"
        href="http://discord.com/users/740751379571933265"
        Icon={IconDiscord}
        label="Discord"
      />

      <SocialLink
        help="Visit MVC's"
        href="https://mvc.ink"
        Icon={IconGlobe}
        label="Website"
      />

      <SocialLink
        help="Send MVC an"
        href="mailto:info@mvc.ink"
        Icon={IconMail}
        label="Email"
      />
    </div>
  </div>
</section>
