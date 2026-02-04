<script>
  import { browser } from '$app/environment';
  import { onDestroy, onMount } from 'svelte';

  let animationId;
  let canvas;

  let stars = [];
  let nebulae = [];
  let dust = [];

  const initElements = () => {
    // Stars
    const starCount = Math.floor((canvas.width * canvas.height) / 4000);
    stars = [];
    for (let i = 0; i < starCount; i++) {
      stars.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height,
        size: Math.random() * 2 + 0.5,
        speed: Math.random() * 0.3 + 0.1,
        opacity: Math.random() * 0.8 + 0.2
      });
    }

    // Nebula clouds (large, subtle, slow-moving)
    const nebulaCount = 3 + Math.floor(Math.random() * 2);
    nebulae = [];
    for (let i = 0; i < nebulaCount; i++) {
      nebulae.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height,
        radius: 100 + Math.random() * 200,
        hue: [260, 280, 320, 200, 180][Math.floor(Math.random() * 5)],
        opacity: 0.03 + Math.random() * 0.04,
        drift: (Math.random() - 0.5) * 0.1
      });
    }

    // Cosmic dust particles (tiny, scattered)
    const dustCount = Math.floor((canvas.width * canvas.height) / 8000);
    dust = [];
    for (let i = 0; i < dustCount; i++) {
      dust.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height,
        size: Math.random() * 1.5 + 0.3,
        opacity: Math.random() * 0.3 + 0.1,
        speed: Math.random() * 0.15 + 0.05
      });
    }
  };

  const resizeCanvas = () => {
    canvas.width = canvas.offsetWidth;
    canvas.height = canvas.offsetHeight;

    initElements();
  };

  onMount(() => {
    if (!browser || !canvas) {
      return;
    }

    const canvasContext = canvas.getContext('2d');

    if (!canvasContext) {
      return;
    }

    const animate = () => {
      // Dark space background
      canvasContext.fillStyle = 'hsl(240, 20%, 6%)';
      canvasContext.fillRect(0, 0, canvas.width, canvas.height);

      // Draw nebula clouds (behind everything)
      nebulae.forEach((nebula) => {
        // Slow horizontal drift
        nebula.x += nebula.drift;

        if (nebula.x < -nebula.radius) {
          nebula.x = canvas.width + nebula.radius;
        }

        if (nebula.x > canvas.width + nebula.radius) {
          nebula.x = -nebula.radius;
        }

        // Multi-layered nebula gradient
        const nebulaGradient = canvasContext.createRadialGradient(
          nebula.x,
          nebula.y,
          0,
          nebula.x,
          nebula.y,
          nebula.radius
        );
        nebulaGradient.addColorStop(0, `hsla(${nebula.hue}, 60%, 50%, ${nebula.opacity * 1.5})`);
        nebulaGradient.addColorStop(0.3, `hsla(${nebula.hue}, 50%, 40%, ${nebula.opacity})`);
        nebulaGradient.addColorStop(
          0.6,
          `hsla(${nebula.hue + 20}, 40%, 30%, ${nebula.opacity * 0.5})`
        );
        nebulaGradient.addColorStop(1, 'transparent');

        canvasContext.beginPath();
        canvasContext.arc(nebula.x, nebula.y, nebula.radius, 0, Math.PI * 2);
        canvasContext.fillStyle = nebulaGradient;
        canvasContext.fill();
      });

      // Draw cosmic dust (between nebulae and stars)
      dust.forEach((particle) => {
        particle.opacity += (Math.random() - 0.5) * 0.02;
        particle.opacity = Math.max(0.1, Math.min(0.4, particle.opacity));

        particle.y -= particle.speed;
        if (particle.y < -5) {
          particle.y = canvas.height + 5;
          particle.x = Math.random() * canvas.width;
        }

        canvasContext.beginPath();
        canvasContext.arc(particle.x, particle.y, particle.size, 0, Math.PI * 2);
        canvasContext.fillStyle = `hsla(260, 30%, 70%, ${particle.opacity})`;
        canvasContext.fill();
      });

      // Draw stars (on top)
      stars.forEach((star) => {
        star.opacity += (Math.random() - 0.5) * 0.05;
        star.opacity = Math.max(0.3, Math.min(1, star.opacity));

        star.y -= star.speed;
        if (star.y < -10) {
          star.y = canvas.height + 10;
          star.x = Math.random() * canvas.width;
        }

        // Outer glow
        const glowGradient = canvasContext.createRadialGradient(
          star.x,
          star.y,
          0,
          star.x,
          star.y,
          star.size * 4
        );
        glowGradient.addColorStop(0, `hsla(220, 80%, 90%, ${star.opacity * 0.6})`);
        glowGradient.addColorStop(0.3, `hsla(260, 70%, 80%, ${star.opacity * 0.3})`);
        glowGradient.addColorStop(1, 'transparent');

        canvasContext.beginPath();
        canvasContext.arc(star.x, star.y, star.size * 4, 0, Math.PI * 2);
        canvasContext.fillStyle = glowGradient;
        canvasContext.fill();

        // Bright core
        const coreGradient = canvasContext.createRadialGradient(
          star.x,
          star.y,
          0,
          star.x,
          star.y,
          star.size
        );
        coreGradient.addColorStop(0, `hsla(0, 0%, 100%, ${star.opacity})`);
        coreGradient.addColorStop(0.5, `hsla(200, 80%, 95%, ${star.opacity * 0.8})`);
        coreGradient.addColorStop(1, 'transparent');

        canvasContext.beginPath();
        canvasContext.arc(star.x, star.y, star.size, 0, Math.PI * 2);
        canvasContext.fillStyle = coreGradient;
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
