<script lang="ts">
	// import BgVideo from '$lib/assets/video.mp4';
	// import { sound } from '$lib/states/sound.svelte';
	import Dancing1 from '$lib/components/ui/hero/dancing-note-1.svelte';
	import Dancing2 from '$lib/components/ui/hero/dancing-note-2.svelte';
	import Mathilde from '$lib/assets/Mathilde.jpeg';
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
<div class="z-5 flex h-full w-full flex-row justify-center gap-10 p-10 lg:p-20">
	<div class="relative flex h-1/3 w-full flex-col items-center gap-10 lg:h-full lg:w-1/3">
		<Dancing1
			class="absolute -top-10 left-0 z-20 h-44 w-44 animate-[bounce_1.5s_infinite]"
			color="#df7566"
		/>
		<img
			class="z-10 h-auto rounded-full object-cover lg:h-auto lg:w-full"
			src={Mathilde}
			alt="Mathilde Guer"
		/>

		<div class="z-10 text-center text-4xl font-black">
			Musicothérapie clinicienne et professeure de piano
		</div>

		<Dancing1
			class="absolute bottom-1/3 left-20 z-20 h-24 w-24 animate-[wiggle_1s_infinite]"
			color="#75A39B"
		/>
		<Dancing2
			class="absolute -top-10 right-0 h-36 w-36 animate-[bounce_1s_infinite]"
			color="#75A39B"
		/>
		<Dancing2
			class="absolute bottom-1/2 right-0 z-20 h-32 w-32 animate-[wiggle_1.25s_infinite]"
			color="#df7566"
		/>
	</div>
	<!-- <section class="justify-center lg:w-1/2">
		<h2 class="text-4xl font-black">Bonjour!</h2>
		<br /> <br />
		<p class="text-sm font-semibold lg:text-xl">
			Je m’appelle Mathilde Guer, j’exerce le métier de musicothérapeute clinicienne et de
			professeur de piano. <br />
			Mon parcours musical à débuté durant mon enfance par l’apprentissage de la guitare puis du piano
			en conservatoire à rayonnement régional (Annecy et Montpellier). <br /> <br />
			Aujourd’hui j'apprends la clarinette en autodidacte. Je me suis également formée à l’université
			Paul Valéry Montpellier 3 en tant que musicothérapeute clinicienne. Ce diplôme est reconnu par
			la Fédération Française des Musicothérapeutes (voir liens utiles). <br /> <br />
			J’ai choisi d’utiliser le piano comme outil d’enseignement pour partager un savoir créatif, d’expression,
			et d’évasion pouvant être utilisé pour son bien être tout au long de notre vie. Mon métier de musicothérapeute
			clinicienne m’est venu par la volonté d’utiliser les divers effets de la musique, sur la cognitif,
			l’affectif, le social et le moteur, dans un cadre de soin thérapeutique
		</p>
	</section> -->
</div>
