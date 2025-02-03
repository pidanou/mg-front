<script lang="ts">
	import { Motion, useTransform, AnimatePresence, useMotionValue, useSpring } from 'svelte-motion';
	import { cn } from '$lib/utils/cn';
	import { onMount } from 'svelte';

	export let items: {
		id: number;
		name: string;
		designation: string;
		image: string;
	}[];

	let hoveredIndex: number | null = null;
	const springConfig = { stiffness: 100, damping: 5 };
	const x = useMotionValue(0); // going to set this value on mouse move
	// rotate the tooltip
	const rotate = useSpring(useTransform(x, [-90, 90], [-20, 20]), springConfig);
	// translate the tooltip
	const translateX = useSpring(useTransform(x, [-90, 90], [-20, 20]), springConfig);
	const handleMouseMove = (event: MouseEvent) => {
		// @ts-ignore
		const halfWidth = event.target?.offsetWidth / 2;
		x.set(event.offsetX - halfWidth); // set the x value, which is then used in transform and rotate
	};
	let userHover = false;

	function simulateHover() {
		let currentIndex = 0;
		setInterval(() => {
			if (userHover) return;
			x.set((Math.random() * 2 - 1) * 100);
			hoveredIndex = items[currentIndex].id; // Set hovered index to simulate hover
			currentIndex = (currentIndex + 1) % items.length; // Cycle through the items
		}, 5000); // Trigger every 5 seconds
	}

	onMount(() => {
		simulateHover(); // Start simulating hover when component is mounted
	});
</script>

<div
	class="group flex h-full w-full flex-row flex-wrap items-center justify-center gap-6 2xl:flex-col"
>
	{#each items as item, idx (item.name)}
		<div
			role="img"
			aria-label="tooltip"
			on:mouseenter={() => {
				hoveredIndex = item.id;
				userHover = true;
			}}
			on:mouseleave={() => {
				hoveredIndex = null;
				userHover = false;
			}}
		>
			<AnimatePresence show={true}>
				{#if hoveredIndex === item.id}
					<Motion
						let:motion
						initial={{ opacity: 0, y: 30, scale: 0.6 }}
						animate={{
							opacity: 1,
							y: 0,
							scale: 1,
							transition: {
								type: 'spring',
								stiffness: 260,
								damping: 10
							}
						}}
						exit={{ opacity: 0, y: 20, scale: 0.6 }}
						style={{
							translateX: translateX,
							rotate: rotate,
							whiteSpace: 'nowrap'
						}}
					>
						<div
							use:motion
							class="absolute z-50 flex w-52 min-w-fit flex-col items-center justify-center rounded-sm bg-black px-4 py-2 text-xs shadow-xl"
						>
							<div class="relative z-30 whitespace-nowrap text-base font-bold text-white">
								{item.name}
							</div>
							<div class="text-xs text-white">{item.designation}</div>
						</div>
					</Motion>
				{/if}
			</AnimatePresence>
			<div class={`h-full w-full`} style="animation-delay: {idx * 100}ms;">
				<img
					on:mousemove={handleMouseMove}
					height={300}
					width={300}
					src={item.image}
					alt={item.name}
					class="relative !m-0 h-20 w-auto rounded-full object-cover object-top !p-0 transition duration-500 group-hover:z-30 group-hover:scale-105 xl:h-40"
				/>
			</div>
		</div>
	{/each}
</div>
