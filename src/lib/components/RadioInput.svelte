<script>
  import IconCircle from '$lib/components/Icons/Circle.svelte';

  let { checked = $bindable(), label, value } = $props();
</script>

<label
  class="flex cursor-pointer items-center gap-3 rounded-lg bg-background px-4 py-3 transition-colors hover:bg-muted"
>
  <button
    class="aspect-square h-4 w-4 rounded-full border border-primary text-primary ring-offset-background focus:outline-hidden focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:cursor-not-allowed disabled:opacity-50"
    type="button"
    role="radio"
    data-state={checked === value ? 'checked' : 'unchecked'}
    aria-checked={checked === value}
    aria-label={label}
    {value}
    id={`delivery-${value}`}
    onclick={() => (checked = value)}
  >
    {#if checked === value}
      <span class="flex items-center justify-center">
        <IconCircle class="h-2.5 w-2.5 fill-current text-current" />
      </span>
    {/if}
  </button>

  <span class="text-sm text-foreground">{label}</span>
</label>
