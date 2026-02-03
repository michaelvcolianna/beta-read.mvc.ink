<script>
  import { browser } from '$app/environment';
  import { onDestroy, onMount } from 'svelte';

  let canvas = $state();

  onMount(() => {
    if (!browser || !canvas) {
      return;
    }

    const canvasContext = canvas.getContext('2d');

    if (!canvasContext) {
      return;
    }

    let animationId;
    let particles = [];

    const resizeCanvas = () => {
      canvas.width = canvas.offsetWidth;
      canvas.height = canvas.offsetHeight;

      initParticles();
    };

    const initParticles = () => {
      const particleCount = Math.floor((canvas.width * canvas.height) / 4000);

      particles = [];

      for (let i = 0; i < particleCount; i++) {
        particles.push({
          x: Math.random() * canvas.width,
          y: Math.random() * canvas.height,
          size: Math.random() * 2 + 0.5,
          speed: Math.random() * 0.3 + 0.1,
          opacity: Math.random() * 0.8 + 0.2
        });
      }
    };

    const animate = () => {
      canvasContext.clearRect(0, 0, canvas.width, canvas.height);

      particles.forEach((particle) => {
        // Twinkling effect
        particle.opacity += (Math.random() - 0.5) * 0.05;
        particle.opacity = Math.max(0.2, Math.min(1, particle.opacity));

        // Slow drift upward
        particle.y -= particle.speed;
        if (particle.y < -10) {
          particle.y = canvas.height + 10;
          particle.x = Math.random() * canvas.width;
        }

        // Draw particle with glow
        const gradient = canvasContext.createRadialGradient(
          particle.x,
          particle.y,
          0,
          particle.x,
          particle.y,
          particle.size * 2
        );
        gradient.addColorStop(0, `hsla(260, 60%, 80%, ${particle.opacity})`);
        gradient.addColorStop(0.5, `hsla(175, 60%, 75%, ${particle.opacity * 0.5})`);
        gradient.addColorStop(1, 'transparent');

        // Outer particle
        canvasContext.beginPath();
        canvasContext.arc(particle.x, particle.y, particle.size * 2, 0, Math.PI * 2);
        canvasContext.fillStyle = gradient;
        canvasContext.fill();

        // Core of particle
        canvasContext.beginPath();
        canvasContext.arc(particle.x, particle.y, particle.size * 0.5, 0, Math.PI * 2);
        canvasContext.fillStyle = `hsla(0, 0%, 100%, ${particle.opacity})`;
        canvasContext.fill();
      });

      animationId = requestAnimationFrame(animate);
    };

    resizeCanvas();
    animate();

    window.addEventListener('resize', resizeCanvas);
  });

  onDestroy(() => {
    if (!browser) {
      return;
    }

    window.removeEventListener('resize', resizeCanvas);
    cancelAnimationFrame(animationId);
  });
</script>

<canvas
  bind:this={canvas}
  aria-hidden="true"
  class="pointer-events-none absolute inset-0 h-full w-full"
></canvas>
