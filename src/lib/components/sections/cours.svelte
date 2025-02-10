<script>
	import { AnimatedTooltip } from '$lib/components/ui/animated-tooltip';
	import * as Accordion from '$lib/components/ui/accordion/index';
	import Classique from '$lib/assets/PianoClassique.jpg';
	import Actuel from '$lib/assets/PianoMusiqueActuelle.jpg';
	import Film from '$lib/assets/MusiqueDeFilm.jpg';
	import Improvisation from '$lib/assets/Improvisation.jpg';
	import Harmonisation from '$lib/assets/Harmonisation.jpg';

	const content = [
		{
			title: 'Méthodologie',
			description: `Grâce à ma formation en musicothérapie, je sais m'adapter aux besoins uniques de chaque élève. Lors de nos cours, nous travaillons généralement sur un morceau choisi par l'élève. Nous réalisons également des exercices et des morceaux ciblés en fonction des besoins spécifiques de l'élève. Je m'assure que l'apprentissage soit agréable, en mettant l'accent sur le plaisir musical et le confort de jeu.`
		},
		{
			title: 'Eveil musical',
			description:
				'L’éveil musical concerne les enfants de moins de 5 ans. L’enfant entre dans l’univers de la musique à travers la découverte et l’improvisation instrumentale ou vocale.'
		},
		{
			title: 'Formation musicale',
			description:
				"Chaque cours de piano ou d’éveil musical est agrémenté d'éléments de formation musicale. Cependant vous pouvez également prendre des cours complémentaires de formation musicale afin d’enrichir votre compréhension et votre écoute musicale."
		}
	];

	const people = [
		{
			id: 1,
			name: 'Classique',
			designation:
				'De l’époque baroque (Jean-Sébastien Bach) <br> en passant par le romantisme (Frédéric Chopin) <br> jusqu’à l’époque contemporaine (Philip Glass).',
			image: Classique
		},
		{
			id: 2,
			name: 'Musique actuelle',
			designation: 'Variété, Pop Rock, Jazz…',
			image: Actuel
		},
		{
			id: 3,
			name: 'Musique de film',
			designation: 'Intouchable, Interstellar, Amélie Poulain et d’autres...',
			image: Film
		},
		{
			id: 4,
			name: 'Improvision',
			designation: 'Apprentissage de l’expression musicale à travers le piano.',
			image: Improvisation
		},
		{
			id: 5,
			name: 'Harmonisation',
			designation: 'Apprentissage des différentes tonalités et de leurs accords associés.',
			image: Harmonisation
		}
	];
</script>

<div class="flex w-screen flex-col gap-6 p-10 lg:p-20 2xl:flex-row-reverse">
	<div class="flex w-full flex-col items-start justify-start 2xl:h-full 2xl:w-1/2 2xl:p-20">
		<div class="text-4xl font-bold 2xl:text-6xl">
			L'apprentissage du piano
			<span class="font-black text-[#6d83d3] hover:italic hover:underline">adapté</span>
			à vos envies
		</div>
		<Accordion.Root type="single" class="mt-10 w-full 2xl:mt-36">
			{#each content as item, index (item.title + index)}
				<Accordion.Item class="border-none" value={index.toFixed()}>
					<Accordion.Trigger class="text-xl font-extrabold 2xl:text-2xl"
						>{item.title}</Accordion.Trigger
					>
					<Accordion.Content class="text-lg font-semibold"
						>{@html item.description}</Accordion.Content
					>
				</Accordion.Item>
			{/each}
		</Accordion.Root>
	</div>
	<div class="w-full 2xl:h-screen 2xl:w-1/2">
		<div class="flex h-full w-full 2xl:p-20">
			<AnimatedTooltip items={people} />
		</div>
	</div>
</div>
