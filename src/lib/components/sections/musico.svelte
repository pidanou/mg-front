<script>
	import { AnimatedTooltip } from '$lib/components/ui/animated-tooltip';
	import * as Accordion from '$lib/components/ui/accordion/index';
	import Newborn from '$lib/assets/NouveauNe.jpg';
	import Child from '$lib/assets/Enfants.jpg';
	import Teen from '$lib/assets/Ado.jpg';
	import Adult from '$lib/assets/Adulte.jpg';
	import Senior from '$lib/assets/PersonnesAgees.jpg';
	import End from '$lib/assets/FinDeVie.jpg';
	import Institution from '$lib/assets/Hopital.jpg';
	import Handicap from '$lib/assets/Handicap.jpg';

	const content = [
		{
			title: 'Pourquoi utiliser la musique ?',
			description:
				'Jouer et écouter de la musique stimule la motivation, la mémoire, l’attention, les compétences sociales, la motricité, les émotions… Elle peut également réduire les tensions musculaires, la fréquence cardiaque et la pression artérielle.'
		},
		{
			title: 'Les outils du musicothérapeute',
			description:
				'J’utilise trois grands outils en musicothérapie : la musicothérapie active, la musicothérapie réceptive et la détente psychomusicale. <br><br> 🎹  En musicothérapie active, nous sélectionnons des instruments faciles d’utilisation ne nécessitant aucune compétence musicale.<br>👂  En musicothérapie réceptive, nous écoutons de la musique en lien avec vos objectifs, suivi d’un espace d’échange. <br>🧘  En détente psychomusicale, vous pouvez vous laisser porter par la musique que je vous joue en direct.'
		},
		{
			title: "Cadre d'intervention",
			description:
				'Chaque prise en charge débute par un bilan en musicothérapie en trois étapes (un entretien, un bilan en musicothérapie active et un bilan en musicothérapie réceptive) afin d’établir ensemble un projet personnalisé adapté à vos besoins. <br><br> La musicothérapie se pratique en séance de groupe ou en individuel durant en moyenne trois-quarts d’heure adaptable en fonction de chacun. <br><br>Les séances ont lieu dans les alentours de Sallanches (74).'
		},
		{
			title: 'Public visé',
			description:
				'La musicothérapie s’adapte à toutes les personnes ayant à cœur l’amélioration de leur qualité de vie en se basant sur les bienfaits de la musique.'
		},
		{
			title: 'Liens utiles',
			description: `<a class="underline" aria-label="Plus d'information sur les musicothérapeutes" href="https://www.musicotherapeutes.fr" target="_blank">musicotherapeutes.fr</a> <br> <a class="underline" aria-label="Plus d'indormation sur la musicothérapie" href="https://francemusicotherapie.fr" target="_blank">francemusicotherapie.fr</a>`
		}
	];

	const people = [
		{
			id: 1,
			name: 'Nouveau-né',
			designation: 'Diminution de l’anxiété des nouveau-nés, relation parents-enfants…',
			image: Newborn
		},
		{
			id: 2,
			name: 'Enfant',
			designation:
				'Difficultés scolaires, difficultés sociales, <br> expression des émotions,  addictions aux écrans…',
			image: Child
		},
		{
			id: 3,
			name: 'Adolescent',
			designation: `Confiance en soi, expression des émotions, <br> diminutions de l'anxiété, difficultés scolaires, <br> difficultés sociales, addictions…`,
			image: Teen
		},
		{
			id: 4,
			name: 'Adulte',
			designation:
				'Diminution de l’anxiété, <br> diminution des douleurs chroniques,<br> augmentation de la motivation, addictions...',
			image: Adult
		},
		{
			id: 5,
			name: 'Senior',
			designation:
				'Stimulation cognitive, maintien de l’autonomie, <br> stimulation motrice, diminution de l’anxiété, <br> diminution de la douleur...',
			image: Senior
		},
		{
			id: 6,
			name: 'Personne en fin de vie',
			designation:
				'Diminution de l’anxiété, diminution des douleurs, <br> acceptation de la mort, rappel des souvenirs…',
			image: End
		},
		{
			id: 7,
			name: 'Personnes en situation de handicap',
			designation: 'Amélioration de la qualité de vie...',
			image: Handicap
		},
		{
			id: 8,
			name: 'Institution',
			designation:
				'Amélioration de la qualité de vie des patients ou des résidents en collaboration avec l’équipe pluridisciplinaire.',
			image: Institution
		}
	];
</script>

<div class="flex w-screen flex-col gap-6 p-10 lg:p-20 2xl:flex-row">
	<div class="flex w-full flex-col items-start justify-start 2xl:h-full 2xl:w-2/5 2xl:p-20">
		<div class="text-4xl font-bold 2xl:text-5xl">
			La <br /><span class="font-black text-[#de7433] hover:italic hover:underline"
				>musicothérapie</span
			>,<br />
			une démarche de soin par la musique
			<span class="font-black text-[#de7433] hover:italic hover:underline">pour tous</span>
		</div>
		<Accordion.Root type="single" class="mt-10 w-full">
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
	<div class="w-full 2xl:h-screen 2xl:w-3/5">
		<div class="flex h-full w-full 2xl:p-20">
			<AnimatedTooltip items={people} />
		</div>
	</div>
</div>
