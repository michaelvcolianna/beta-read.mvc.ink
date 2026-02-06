<script>
  import Link from '$lib/components/Link.svelte';
</script>

<footer id="privacy" class={['w-full', 'scroll-mt-8', 'bg-muted/30', 'py-10', 'md:py-16']}>
  <div class={['section-container']}>
    <div class={['mx-auto', 'max-w-2xl', 'text-center']}>
      <h3 class={['mb-4', 'font-display', 'text-lg', 'font-semibold', 'text-foreground']}>
        Privacy Policy
      </h3>

      <div class={['space-y-3', 'text-sm', 'text-muted-foreground']}>
        <p>
          Your privacy matters. Information submitted through this site is used solely by MVC to
          communicate directly with you about this book. Your data is never sold, shared, or used
          for marketing purposes.
        </p>

        <p>
          Once you complete your beta read, your information will be deleted, unless otherwise
          specified by you. By submitting the form, you consent to receiving direct communication
          from MVC regarding your beta reader copy request.
        </p>
      </div>

      <div
        class={['mt-8', 'border-t', 'border-border', 'pt-6', 'text-xs', 'text-muted-foreground']}
      >
        <p>
          © 2026 MVC. All rights reserved. <span class={['hidden', 'md:inline']}
            >Header image by <Link href="https://www.artstation.com/yaroslavus"
              >Jaroslaw Marcinek</Link
            >.</span
          >
        </p>
      </div>
    </div>
  </div>
</footer>
