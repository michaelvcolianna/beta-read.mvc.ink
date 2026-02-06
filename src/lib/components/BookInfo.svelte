<script>
  let { green, help, Icon, label, red } = $props();

  const textColor = $derived.by(() => {
    let color = 'popover';

    if (green) {
      color = 'secondary';
    }

    if (red) {
      color = 'accent';
    }

    return `text-${color}-foreground`;
  });
</script>

<div
  class={[
    'flex',
    'items-center',
    'gap-2',
    'rounded-full',
    'px-4',
    'py-2',
    green && 'bg-secondary',
    red && 'bg-accent/30'
  ]}
>
  <Icon class={['h-4', 'w-4', textColor]} />

  <span class={['sr-only']}>{help}:</span>

  <span class={['text-sm', 'font-medium', textColor]}>{label}</span>
</div>
