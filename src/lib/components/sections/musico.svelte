<script>
	import { StickyScrollReveal } from '$lib/components/ui/stick-scroll';
	const content = [
		{
			title: 'Collaborative Editing',
			description:
				'Work together in real time with your team, clients, and stakeholders. Collaborate on documents, share ideas, and make decisions quickly. With our platform, you can streamline your workflow and increase productivity.'
		},
		{
			title: 'Real time changes',
			description:
				'See changes as they happen. With our platform, you can track every modification in real time. No more confusion about the latest version of your project. Say goodbye to the chaos of version control and embrace the simplicity of real-time updates.'
		},
		{
			title: 'Version control',
			description:
				"Experience real-time updates and never stress about version control again. Our platform ensures that you're always working on the most recent version of your project, eliminating the need for constant manual updates. Stay in the loop, keep your team aligned, and maintain the flow of your work without any interruptions."
		},
		{
			title: 'Running out of content',
			description:
				"Experience real-time updates and never stress about version control again. Our platform ensures that you're always working on the most recent version of your project, eliminating the need for constant manual updates. Stay in the loop, keep your team aligned, and maintain the flow of your work without any interruptions."
		}
	];
</script>

<div class="h-screen w-screen">
	<div class="p-10 text-5xl font-bold text-slate-900">
		Une démarche de soin <br /> par la musique
	</div>
	<div class="potato m-10 h-[35rem] w-1/2">
		<StickyScrollReveal {content} />
	</div>
</div>

<style>
	.potato {
		background-color: #f6f3d8;
		border-radius: 55% 45% 50% 55% / 50% 60% 40% 50%;
		overflow: hidden;
	}
</style>
