<script>
  import IconBluesky from '$lib/components/Icons/Bluesky.svelte';
  import IconDiscord from '$lib/components/Icons/Discord.svelte';
  import IconGlobe from '$lib/components/Icons/Globe.svelte';
  import IconMail from '$lib/components/Icons/Mail.svelte';

  let { help, href, icon, label } = $props();

  const icons = {
    bluesky: IconBluesky,
    discord: IconDiscord,
    globe: IconGlobe,
    mail: IconMail
  };

  let Icon = $derived(icons[icon]);
</script>

<a
  {href}
  class="group flex items-center gap-3 rounded-full bg-card px-5 py-3 transition-all hover:scale-105 hover:bg-primary"
>
  <Icon class="h-5 w-5 text-primary transition-colors group-hover:text-primary-foreground" />

  <span class="sr-only">{help}</span>

  <span
    class="text-sm font-medium text-foreground transition-colors group-hover:text-primary-foreground"
    >{label}</span
  >
</a>
