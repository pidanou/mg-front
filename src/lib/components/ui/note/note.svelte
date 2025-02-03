<script lang="ts">
	import { cn } from '$lib/utils.js';
	let {
		transition,
		active,
		duration,
		class: className
	}: { transition: any; active: boolean; duration: number; class: string } = $props();
</script>

<svg
	xmlns="http://www.w3.org/2000/svg"
	viewBox="0 0 24 24"
	fill="none"
	stroke="currentColor"
	stroke-width="3"
	stroke-linecap="round"
	stroke-linejoin="round"
	class={cn('lucide lucide-music-2 flex-no-shrink h-12 w-12', className)}
	><circle cx="8" cy="18" r="4" />
	{#if active}
		<path transition:transition={{ duration }} d="M12 18V2l7 4" />
	{/if}
</svg>
