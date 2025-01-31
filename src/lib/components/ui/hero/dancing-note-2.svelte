<script>
	import { cn } from '$lib/utils/cn';
	let { class: className = '', fill = 'fill-[#df7566]' } = $props();
</script>

<div class={cn('animate-[bounce_1.5s_infinite]', className)}>
	<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 220.63 151.34"
		><defs></defs><g id="Layer_2" data-name="Layer 2"
			><g id="Layer_1-2" data-name="Layer 1">
				<path
					class={cn('', fill)}
					d="M154.66,140.37c2.75-5.05,5.44-9.85,8-14.74.89-1.71,1.75-1.91,3.31-.86,4.55,3.06,9.72,3.35,15,3.16.89,0,1.77-.1,3-.17-.46,1-.71,1.65-1,2.25-3.63,6.66-14.36,2.37-18.74,1.81-.49-.06-1.3.72-1.63,1.3-2.14,3.81-4.17,7.67-6.28,11.49a6.16,6.16,0,0,1-6.52,3.08,4.5,4.5,0,0,1-3.61-5.61,4.85,4.85,0,0,1,6.31-2.81C153.11,139.56,153.79,140,154.66,140.37Z"
				/>
			</g></g
		></svg
	>
</div>
