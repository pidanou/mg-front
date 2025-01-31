<script>
	import { AnimatedTooltip } from '$lib/components/ui/animated-tooltip';
	import * as Accordion from '$lib/components/ui/accordion/index';
	import Newborn from '$lib/assets/NouveauNe.jpg';
	import Child from '$lib/assets/EnfantMusique.png';
	import Teen from '$lib/assets/Adolescent.png';
	import Adult from '$lib/assets/Adulte.jpg';
	import Senior from '$lib/assets/PersonnesAgees.jpg';
	import End from '$lib/assets/FinDeVie.jpg';
	import Institution from '$lib/assets/Hopital.jpg';
	import Handicap from '$lib/assets/Handicap.jpg';

	const content = [
		{
			title: 'Pourquoi utiliser la musique ?',
			description:
				'Jouer et écouter de la musique stimule la motivation, la mémoire, l’attention, les compétences sociales, la motricité, les émotions… Elle peut également réduire les tensions musculaires, la fréquence cardiaque, la pression artérielle.'
		},
		{
			title: 'Les outils du musicothérapeute',
			description:
				'J’utilise trois outils en musicothérapie, la musicothérapie active, la musicothérapie réceptive et la détentes psychomusicale. <br><br> En musicothérapie active, nous utilisons des instruments faciles d’utilisation ne nécessitant aucune compétence musicale. <br><br> En musicothérapie réceptive, nous écoutons de la musique en lien avec vos objectifs, suivi d’un espace d’échange. <br><br>En détente psychomusicale, vous pouvez vous laisser porter par la musique que je vous joue en direct. '
		},
		{
			title: "Cadre d'intervention",
			description:
				'Chaque prise en charge débute par un bilan en musicothérapie en trois étapes ( un entretien, un bilan en musicothérapie active et un bilan en musicothérapie réceptive)  afin d’établir ensemble un projet personnalisé adapté à vos besoins. <br><br> La musicothérapie se pratique en séance de groupe ou en individuel durant en moyenne 4/3 d’heures adaptable en fonction de chacun. <br><br> Les séances ont lieu aux alentours de Sallanches (74).'
		},
		{
			title: 'Public visé',
			description:
				'La musicothérapie s’adapte à divers besoins que vous soyez une personne en situation de handicap, que vous soyez hospitalisé ou non à partir du moment où vous êtes réceptifs à la musique.'
		},
		{
			title: 'Liens utiles',
			description:
				'Chaque prise en charge débute par un bilan en musicothérapie en trois étapes ( un entretien, un bilan en musicothérapie active et un bilan en musicothérapie réceptive)  afin d’établir ensemble un projet personnalisé adapté à vos besoins. <br><br> La musicothérapie se pratique en séance de groupe ou en individuel durant en moyenne 4/3 d’heures adaptable en fonction de chacun. <br><br> Les séances ont lieu aux alentours de Sallanches (74).'
		}
	];

	const people = [
		{
			id: 1,
			name: 'Nouveau-né',
			designation: 'Diminution de l’anxiété des nouveaux-nés, relation parents enfants…',
			image: Newborn
		},
		{
			id: 2,
			name: 'Enfant',
			designation:
				'difficultés scolaires, difficultés sociales, expression des émotions,  addictions aux écrans…',
			image: Child
		},
		{
			id: 3,
			name: 'Adolescent',
			designation: `confiance en soi, expression des émotions, diminutions de l'anxiété, difficultés scolaires, difficultés sociales, addictions…`,
			image: Teen
		},
		{
			id: 4,
			name: 'Adulte',
			designation:
				'diminution de l’anxiété, diminution des douleurs chroniques, augmentation de la motivation, addictions',
			image: Adult
		},
		{
			id: 5,
			name: 'Senior',
			designation:
				'stimulation cognitive, maintien de l’autonomie, stimulation motrice, diminution de l’anxiété, diminution de la douleur',
			image: Senior
		},
		{
			id: 6,
			name: 'Personne en fin de vie',
			designation:
				'diminution de l’anxiété, diminution des douleurs, acceptation de la mort, rappel des souvenirs…',
			image: End
		},
		{
			id: 7,
			name: 'Institution',
			designation:
				'amélioration de la qualité de vie des patients ou résidents en collaboration avec l’équipe pluridisciplinaire.',
			image: Institution
		},
		{
			id: 8,
			name: 'Personnes en situation de handicap',
			designation: 'amélioration de la qualité de vie',
			image: Handicap
		}
	];
</script>

<div class="flex w-screen flex-col gap-6 lg:h-screen lg:flex-row lg:p-20">
	<div class="flex flex-col items-start justify-start p-10 lg:h-full lg:w-1/2 lg:p-20">
		<div class="text-5xl font-bold">
			La
			<span class="font-black text-[#de7466] hover:italic hover:underline">musicothérapie</span>,<br
			/>
			une démarche de soin par la musique
			<span class="font-black text-[#de7466] hover:italic hover:underline">pour tous</span>
		</div>
		<Accordion.Root type="single" class="mt-16 w-full">
			{#each content as item, index (item.title + index)}
				<Accordion.Item class="border-none" value={index.toFixed()}>
					<Accordion.Trigger class="text-3xl font-extrabold">{item.title}</Accordion.Trigger>
					<Accordion.Content class="text-sm">{@html item.description}</Accordion.Content>
				</Accordion.Item>
			{/each}
		</Accordion.Root>
	</div>
	<div class="relative h-full lg:w-1/2">
		<div class="flex h-full w-full p-20">
			<AnimatedTooltip items={people} />
		</div>
	</div>
</div>
