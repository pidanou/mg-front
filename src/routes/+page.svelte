<script lang="ts">
	import { onMount } from 'svelte';
	import Piano from '$lib/components/ui/side-menu/side-menu.svelte';
	import Musico from '$lib/components/sections/musico.svelte';

	let y: number | undefined = $state();
	let scrollContainer: any;

	function onscroll() {
		y = scrollContainer?.scrollTop || 0; // Update y when scrolling
	}

	let vh = 0;

	function updateVH() {
		vh = window.innerHeight; // 1vh = 1% of viewport height
	}

	function onclick(section: string) {
		const anchor = document.getElementById(section);
		scrollContainer.scrollTo({
			top: anchor?.offsetTop,
			behavior: 'smooth'
		});
	}

	onMount(() => {
		updateVH(); // Set initially
		window.addEventListener('resize', updateVH); // Update on resize
		return () => window.removeEventListener('resize', updateVH);
	});

	let page = $derived(Math.round(y ? y / vh : 0));
</script>

<div class="absolute right-0 m-0 flex h-screen flex-col items-center justify-center">
	<Piano active={page} {onclick} />
</div>
<div
	bind:this={scrollContainer}
	{onscroll}
	class="h-screen snap-y snap-mandatory overflow-y-scroll"
>
	<section
		id="0"
		class="flex h-screen snap-mandatory snap-center items-center justify-center bg-blue-100"
	>
		{page}
	</section>
	<section
		id="1"
		class="flex h-screen snap-mandatory snap-center items-center justify-center bg-red-100"
	>
		{page}
	</section>
	<section
		id="2"
		class="flex h-screen snap-mandatory snap-center items-center justify-center bg-green-100"
	>
		<Musico />
	</section>
	<section
		id="3"
		class="flex h-screen snap-mandatory snap-center items-center justify-center bg-pink-100"
	>
		{page}
	</section>
</div>
