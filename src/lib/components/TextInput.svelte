<script>
  import FieldLabel from '$lib/components/FieldLabel.svelte';
  import RequiredStar from '$lib/components/RequiredStar.svelte';

  let { label, ...props } = $props();
</script>

<div class="space-y-2">
  <FieldLabel forId={props.id}>
    {label}

    {#if props.required}
      <RequiredStar />
    {/if}
  </FieldLabel>

  <input
    class="flex h-10 w-full rounded-md border border-input bg-background px-3 py-2 text-base ring-offset-background file:border-0 file:bg-transparent file:text-sm file:font-medium file:text-foreground placeholder:text-muted-foreground focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 focus-visible:outline-hidden disabled:cursor-not-allowed disabled:opacity-50 md:text-sm"
    name={props.id}
    {...props}
  />
</div>
