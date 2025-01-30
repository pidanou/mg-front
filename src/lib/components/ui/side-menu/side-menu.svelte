<script lang="ts">
	let { active, onclick }: { active: number; onclick: Function } = $props();
</script>

<div class="flex flex-col items-end font-bold">
	<button onclick={() => onclick('0')} class="white fa {active === 0 ? 'wide' : ''}">Accueil</button
	>
	<div class="black as"></div>
	<button onclick={() => onclick('1')} class="white sol {active === 1 ? 'wide' : ''}"
		>A propos de moi</button
	>
	<div class="black gs"></div>
	<button onclick={() => onclick('2')} class="white la {active === 2 ? 'wide' : ''}"
		>Musicothérapie</button
	>
	<div class="black fs"></div>
	<button onclick={() => onclick('3')} class="white si {active === 3 ? 'wide' : ''}"
		>Cours de piano</button
	>
</div>

<style>
	.white {
		height: 4em;
		width: 10em;
		z-index: 1;
		border-radius: 5px 0px 0px 5px;
		background: #fff;
		transition: width 0.3s ease-in-out;
		border: 1px solid #eee;
	}

	.white:hover {
		cursor: pointer;
		width: 12em;
	}

	.black {
		height: 2em;
		width: 2em;
		margin: -1em 0 0 0;
		z-index: 2;
		border-radius: 5px 0 0 5px;
		background: #555555;
	}

	.fa,
	.sol,
	.la,
	.si {
		margin: -1em 0 0 0;
	}

	.wide {
		width: 14em;
	}
	.wide:hover {
		width: 14em;
	}
</style>
