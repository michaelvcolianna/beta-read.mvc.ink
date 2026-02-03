<script>
  let { forId, children } = $props();
</script>

<label
  for={forId}
  class="text-sm leading-none font-medium peer-disabled:cursor-not-allowed peer-disabled:opacity-70"
  >{@render children?.()}</label
>
