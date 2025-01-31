<script lang="ts">
	import Note from '$lib/components/ui/note/note.svelte';
	import { draw } from 'svelte/transition';
	import { cn } from '$lib/utils/cn';
	import Button from '$lib/components/ui/button/button.svelte';
	import { VolumeOff, Volume2 } from 'lucide-svelte/icons';
	import { sound } from '$lib/states/sound.svelte';

	let {
		active,
		onclick,
		class: className
	}: { active: number; onclick: any; class: string } = $props();

	function toggleMute() {
		sound.muted = !sound.muted;
		if (sound.video) {
			sound.video.muted = sound.muted;
		}
	}
</script>

<div class="flex h-full flex-col items-end justify-between gap-6 p-10">
	<div></div>
	<div class="flex flex-col gap-6 max-lg:hidden">
		{#each [0, 1, 2, 3, 4] as index}
			<button onclick={() => onclick(index)} class={cn('z-100 h-min w-min', className)}>
				<Note
					transition={draw}
					active={active === index}
					duration={500}
					size={30}
					class={active === index ? 'animate-wiggle' : ''}
				/>
			</button>
		{/each}
	</div>
	<div>
		<Button onclick={toggleMute} class="hidden rounded-full" size="icon">
			{#if !sound.muted}
				<Volume2 />
			{:else}
				<VolumeOff />
			{/if}
		</Button>
	</div>
</div>
