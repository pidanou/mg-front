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
				'L’éveil musical concerne les enfants de moins de 5 ans. L’enfant découvre l’univers de la musique à travers la découverte et l’improvisation instrumentale ou vocale.'
		},
		{
			title: 'Formation musicale',
			description:
				"Chaque cours de piano ou d’éveil musical est agrémenté d'éléments de formation musicale. Cependant vous pouvez également prendre des cours de formations musicales afin d’enrichir votre compréhension et votre écoute musicale."
		}
	];

	const people = [
		{
			id: 1,
			name: 'Classique',
			designation:
				'de l’époque baroque (Bach) passant le le romantisme (Chopin) à l’époque contemporaine (Glass).',
			image: Classique
		},
		{
			id: 2,
			name: 'Musique actuelle',
			designation: 'les morceaux sont arrangés au niveau de chacun',
			image: Actuel
		},
		{
			id: 3,
			name: 'Musique de film',
			designation: 'Intouchable, Interstellar, Amélie Poulain et d’autres',
			image: Film
		},
		{
			id: 4,
			name: 'Improvision',
			designation: 'apprentissage de l’expression musicale à travers le piano',
			image: Improvisation
		},
		{
			id: 5,
			name: 'Harmonisation',
			designation: 'apprentissage des différentes tonalités et de leurs accords associés',
			image: Harmonisation
		}
	];
</script>

<div class="flex w-screen flex-col gap-6 lg:h-screen lg:flex-row-reverse lg:p-20">
	<div class="flex flex-col items-start justify-start p-10 lg:h-full lg:w-1/2 lg:p-20">
		<div class="text-6xl font-bold">
			L'apprentissage du piano
			<span class="font-black text-[#6d83d3] hover:italic hover:underline">adapté</span>
			à vos capacités
		</div>
		<Accordion.Root type="single" class="mt-10 w-full lg:mt-36">
			{#each content as item, index (item.title + index)}
				<Accordion.Item class="border-none" value={index.toFixed()}>
					<Accordion.Trigger class="text-3xl font-extrabold">{item.title}</Accordion.Trigger>
					<Accordion.Content class="text-lg font-semibold"
						>{@html item.description}</Accordion.Content
					>
				</Accordion.Item>
			{/each}
		</Accordion.Root>
	</div>
	<div class="relative h-full lg:w-1/2">
		<div class="flex h-full w-full px-20 pb-10 lg:p-20">
			<AnimatedTooltip items={people} />
		</div>
	</div>
</div>
