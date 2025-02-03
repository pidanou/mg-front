<script lang="ts">
	import { fly } from 'svelte/transition';
	// import BgVideo from '$lib/assets/video.mp4';
	// import { sound } from '$lib/states/sound.svelte';
	import Dancing1 from '$lib/components/ui/hero/dancing-note-1.svelte';
	import Dancing2 from '$lib/components/ui/hero/dancing-note-2.svelte';
	import Mathilde from '$lib/assets/Mathilde.jpeg';
	import { onMount } from 'svelte';
	import { quintOut } from 'svelte/easing';

	let show = $state(false);
	onMount(() => {
		show = true;
	});
</script>

<!-- svelte-ignore a11y_media_has_caption -->
<!-- <video -->
<!-- 	bind:this={sound.video} -->
<!-- 	class="absolute left-0 top-0 h-full w-full object-cover" -->
<!-- 	autoplay -->
<!-- 	loop -->
<!-- 	playsinline -->
<!-- 	muted={sound.muted} -->
<!-- > -->
<!-- 	<source src={BgVideo} type="video/mp4" /> -->
<!-- </video> -->
<div
	class="flex h-full w-full flex-col items-center justify-center gap-20 p-10 lg:flex-row 2xl:p-20"
>
	{#if show}
		<div
			class="mt-10 flex h-full w-full flex-col items-center justify-center gap-10 2xl:h-full 2xl:w-1/3"
		>
			<div
				class="relative flex flex-col items-center"
				transition:fly={{
					x: show ? 200 : -50,
					duration: 1000,
					easing: quintOut,
					opacity: 0
				}}
			>
				<Dancing1
					class="absolute -top-10 left-0 z-20 h-24 w-24 animate-[bounce_1.5s_infinite] xl:h-44 xl:w-44"
					color="#df7566"
				/>
				<Dancing2
					class="absolute -top-10 right-0 z-0 h-16 w-16  animate-[bounce_1s_infinite] xl:h-36 xl:w-36"
					color="#75A39B"
				/>

				<Dancing1
					class="absolute bottom-5 left-0 z-0 h-10 w-10 animate-[wiggle_1s_infinite] xl:h-24 xl:w-24"
					color="#75A39B"
				/>
				<Dancing2
					class="absolute bottom-10 right-0 z-20 h-20 w-20 animate-[wiggle_1.25s_infinite] xl:h-32 xl:w-32"
					color="#df7566"
				/>
				<img
					class="relative z-10 h-auto w-2/3 rounded-full object-cover 2xl:h-auto 2xl:w-full"
					src={Mathilde}
					alt="Mathilde Guer"
				/>
			</div>
			<div class="z-30 text-center text-4xl font-black">
				Musicothérapeute clinicienne et professeure de piano
			</div>
		</div>
		<section
			class="justify-center 2xl:w-1/2"
			in:fly={{ x: 200, duration: 1000, easing: quintOut, delay: 100 }}
		>
			<h2 class="text-4xl font-black">Bonjour!</h2>
			<br /> <br />
			<p class="text-sm font-semibold 2xl:text-xl">
				Je m’appelle Mathilde Guer, j’exerce le métier de musicothérapeute clinicienne et de
				professeur de piano. <br />
				Mon parcours musical à débuté durant mon enfance par l’apprentissage de la guitare puis du piano
				en conservatoire à rayonnement régional (Annecy et Montpellier). Aujourd’hui j'apprends la clarinette
				en autodidacte. <br /><br /> Je me suis également formée à l’université Paul Valéry
				Montpellier 3 en tant que musicothérapeute clinicienne. Ce diplôme est reconnu par la
				Fédération Française des Musicothérapeutes (voir liens utiles). <br /> <br />
				J’ai choisi d’utiliser le piano comme outil d’enseignement pour partager un savoir créatif, d’expression,
				et d’évasion pouvant être utilisé pour son bien être tout au long de notre vie. Mon métier de
				musicothérapeute clinicienne m’est venu par la volonté d’utiliser les divers effets de la musique,
				sur la cognitif, l’affectif, le social et le moteur, dans un cadre de soin thérapeutique
			</p>
		</section>
	{/if}
</div>
