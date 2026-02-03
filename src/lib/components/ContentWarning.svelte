<script>
  let { children } = $props();
</script>

<li class="flex items-center gap-2">
  <span class="text-primary">•</span>

  <span>{@render children?.()}</span>
</li>
