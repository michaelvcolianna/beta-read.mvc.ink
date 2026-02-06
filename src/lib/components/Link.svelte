<script>
  let { href, children } = $props();
</script>

<a {href} class={['font-medium', 'underline']}>{@render children?.()}</a>
