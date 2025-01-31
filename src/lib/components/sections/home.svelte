<script lang="ts">
	import BgVideo from '$lib/assets/video.mp4';
	import { sound } from '$lib/states/sound.svelte';
	import Hero from '$lib/components/ui/hero/hero.svelte';
	import Dancing1 from '$lib/components/ui/hero/dancing-note-1.svelte';
	import Dancing2 from '$lib/components/ui/hero/dancing-note-2.svelte';
	import Dancing3 from '$lib/components/ui/hero/dancing-note-3.svelte';
	import Dancing4 from '$lib/components/ui/hero/dancing-note-4.svelte';
</script>

<div class="relative h-full w-full p-10">
	<!-- svelte-ignore a11y_media_has_caption -->
	<video
		bind:this={sound.video}
		class="absolute left-0 top-0 h-full w-full object-cover"
		autoplay
		loop
		playsinline
		muted={sound.muted}
	>
		<source src={BgVideo} type="video/mp4" />
	</video>
	<div class="z-5 relative flex h-full w-full flex-col items-center justify-center gap-10 p-10">
		<div class="relative h-full w-full lg:h-auto lg:w-1/3">
			<Hero class="relative" />
			<Dancing1 class="absolute left-0 top-0 w-full delay-500" />
			<Dancing2 class="absolute left-0 top-0 w-full" />
			<Dancing3 class="absolute left-0 top-0 w-full delay-200" fill="fill-[#75A39B]" />
			<Dancing4 class="absolute left-0 top-0 w-full delay-700" fill="fill-[#75A39B]" />
		</div>
	</div>
</div>
