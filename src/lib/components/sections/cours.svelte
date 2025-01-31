<script>
	import { AnimatedTooltip } from '$lib/components/ui/animated-tooltip';
	import * as Accordion from '$lib/components/ui/accordion/index';

	const content = [
		{
			title: 'Méthodologie',
			description: `Grâce à ma formation en musicothérapie, je sais m'adapter aux besoins uniques de chaque élève. Lors de nos cours, nous travaillons généralement sur un morceau choisi par l'élève. Si nécessaire, j'écris moi-même les partitions afin qu'elles correspondent à son niveau. Nous réalisons également des exercices et des morceaux ciblés en fonction des besoins spécifiques de l'élève. Je m'assure que l'apprentissage soit agréable, en mettant l'accent sur le plaisir musical et le confort de jeu. En plus de l'apprentissage des morceaux, nous abordons également les notions de solfège, d'interprétation, et d'improvisation.`
		},
		{
			title: 'Eveil musical',
			description:
				'J’utilise trois outils en musicothérapie, la musicothérapie active, la musicothérapie réceptive et la détentes psychomusicale. <br><br> En musicothérapie active, nous utilisons des instruments faciles d’utilisation ne nécessitant aucune compétence musicale. <br><br> En musicothérapie réceptive, nous écoutons de la musique en lien avec vos objectifs, suivi d’un espace d’échange. <br><br>En détente psychomusicale, vous pouvez vous laisser porter par la musique que je vous joue en direct. '
		},
		{
			title: 'Solfège',
			description:
				'Chaque prise en charge débute par un bilan en musicothérapie en trois étapes ( un entretien, un bilan en musicothérapie active et un bilan en musicothérapie réceptive)  afin d’établir ensemble un projet personnalisé adapté à vos besoins. <br><br> La musicothérapie se pratique en séance de groupe ou en individuel durant en moyenne 4/3 d’heures adaptable en fonction de chacun. <br><br> Les séances ont lieu aux alentours de Sallanches (74).'
		}
	];

	const people = [
		{
			id: 1,
			name: 'Nouveau-né',
			designation: 'Diminution de l’anxiété des nouveaux-nés, relation parents enfants…',
			image:
				'https://images.unsplash.com/photo-1599566150163-29194dcaad36?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=3387&q=80'
		},
		{
			id: 2,
			name: 'Enfant',
			designation: 'difficultés scolaires, difficultés sociales, addictions…',
			image:
				'https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8YXZhdGFyfGVufDB8fDB8fHww&auto=format&fit=crop&w=800&q=60'
		},
		{
			id: 3,
			name: 'Adolescent',
			designation: `confiance en soi, expression des émotions, diminutions de l'anxiété, difficultés scolaires, difficultés sociales, addictions…`,
			image:
				'https://images.unsplash.com/photo-1580489944761-15a19d654956?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NXx8YXZhdGFyfGVufDB8fDB8fHww&auto=format&fit=crop&w=800&q=60'
		},
		{
			id: 4,
			name: 'Adulte',
			designation:
				'diminution de l’anxiété, diminution des douleurs chroniques, augmentation de la motivation, addictions',
			image:
				'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTB8fGF2YXRhcnxlbnwwfHwwfHx8MA%3D%3D&auto=format&fit=crop&w=800&q=60'
		},
		{
			id: 5,
			name: 'Senior',
			designation:
				'stimulation cognitive, maintien de l’autonomie, stimulation motrice, diminution de l’anxiété, diminution de la douleur',
			image:
				'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=3540&q=80'
		},
		{
			id: 6,
			name: 'Personne en fin de vie',
			designation:
				'diminution de l’anxiété, diminution des douleurs, acceptation de la mort, rappel des souvenirs…',
			image:
				'https://images.unsplash.com/photo-1544725176-7c40e5a71c5e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=3534&q=80'
		},
		{
			id: 7,
			name: 'Institution',
			designation: '??',
			image:
				'https://images.unsplash.com/photo-1544725176-7c40e5a71c5e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=3534&q=80'
		}
	];
</script>

<div class="flex w-screen flex-col-reverse gap-6 lg:h-screen lg:flex-row lg:p-20">
	<div class="relative h-full lg:w-1/2">
		<div class="flex h-full w-full p-10">
			<AnimatedTooltip items={people} />
		</div>
	</div>
	<div class="flex flex-col items-start justify-start p-10 lg:h-full lg:w-1/2 lg:p-20">
		<div class="text-5xl font-bold">
			L'apprentissage du piano
			<span class="font-black text-[#6d83d3] hover:italic hover:underline"><br />adapté</span>
			<br />à vos capacités
		</div>
		<Accordion.Root type="single" class="mt-28 w-full">
			{#each content as item, index (item.title + index)}
				<Accordion.Item class="border-none" value={index.toFixed()}>
					<Accordion.Trigger class="text-3xl font-extrabold">{item.title}</Accordion.Trigger>
					<Accordion.Content class="text-sm">{@html item.description}</Accordion.Content>
				</Accordion.Item>
			{/each}
		</Accordion.Root>
	</div>
</div>
