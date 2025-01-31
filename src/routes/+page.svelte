<script lang="ts">
	import { onMount } from 'svelte';
	import Musico from '$lib/components/sections/musico.svelte';
	import Cours from '$lib/components/sections/cours.svelte';
	import Contact from '$lib/components/sections/contact.svelte';

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

<div
	bind:this={scrollContainer}
	{onscroll}
	class="overflow-y-scroll lg:h-screen lg:snap-y lg:snap-mandatory"
>
	<section
		id="0"
		class="flex snap-mandatory snap-center items-center justify-center bg-blue-100 lg:h-screen"
	>
		{page}
	</section>
	<section
		id="1"
		class="flex snap-mandatory snap-center items-center justify-center bg-red-100 lg:h-screen"
	>
		{page}
	</section>
	<section
		id="2"
		class="flex snap-mandatory snap-center items-center justify-center bg-green-100 lg:h-screen"
	>
		<Musico />
	</section>
	<section
		id="3"
		class="flex snap-mandatory snap-center items-center justify-center bg-pink-100 lg:h-screen"
	>
		<Cours />
	</section>
	<section id="4" class="flex snap-mandatory snap-center items-center justify-center lg:h-screen">
		<Contact />
	</section>
</div>
