<script>
	import IconBookOpen from '$lib/components/Icons/BookOpen.svelte';
	import IconCalendarDays from '$lib/components/Icons/CalendarDays.svelte';
	import IconClock from '$lib/components/Icons/Clock.svelte';
	import IconFolderOpen from '$lib/components/Icons/FolderOpen.svelte';

	let { green, help, icon, label, red } = $props();

	const icons = {
		'book-open': IconBookOpen,
		'calendar-days': IconCalendarDays,
		'clock': IconClock,
		'folder-open': IconFolderOpen
	};

	let Icon = $derived(icons[icon]);
</script>

<div
	class={[
		'flex items-center gap-2 rounded-full px-4 py-2',
		green && 'bg-secondary',
		red && 'bg-accent/30'
	]}
>
	<Icon
		class={['h-4 w-4', green && 'text-secondary-foreground', red && 'text-accent-foreground']}
	/>

	<span class="sr-only">{help}:</span>

	<span
		class={[
			'text-sm font-medium',
			green && 'text-secondary-foreground',
			red && 'text-accent-foreground'
		]}>{label}</span
	>
</div>
