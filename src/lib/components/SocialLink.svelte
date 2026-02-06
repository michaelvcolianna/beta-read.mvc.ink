<script>
  let { help, href, Icon, label } = $props();
</script>

<a
  {href}
  class={[
    'group',
    'flex',
    'items-center',
    'gap-3',
    'rounded-full',
    'bg-card',
    'px-5',
    'py-3',
    'transition-all',
    'border-2',
    'border-primary',
    'hover:bg-primary'
  ]}
>
  <Icon
    class={[
      'h-5',
      'w-5',
      'text-primary',
      'transition-colors',
      'group-hover:text-primary-foreground'
    ]}
  />

  <span class={['sr-only']}>{help}</span>

  <span
    class={[
      'text-sm',
      'font-medium',
      'text-foreground',
      'transition-colors',
      'group-hover:text-primary-foreground'
    ]}>{label}</span
  >
</a>
