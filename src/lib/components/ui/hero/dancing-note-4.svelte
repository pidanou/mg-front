<script>
	import { cn } from '$lib/utils/cn';
	let { class: className = '', fill = 'fill-[#df7566]' } = $props();
</script>

<div class={cn('animate-[bounce_3s_infinite]', className)}>
	<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 220.63 151.34"
		><defs></defs><g id="Layer_2" data-name="Layer 2"
			><g id="Layer_1-2" data-name="Layer 1">
				<path
					class={cn('', fill)}
					d="M6.81,128c-2.2-5.31-4.24-10.42-6.43-15.47-.77-1.77-.39-2.57,1.41-3.12,5.24-1.6,8.72-5.44,11.88-9.64.53-.71,1-1.43,1.74-2.42.49,1,.83,1.59,1.1,2.22,2.88,7-7.2,12.65-10.39,15.71-.36.34-.26,1.46,0,2.08,1.61,4.06,3.33,8.07,5,12.11a6.14,6.14,0,0,1-1.71,7,4.49,4.49,0,0,1-6.63-.72,4.84,4.84,0,0,1,1.79-6.67C5.2,128.72,5.92,128.43,6.81,128Z"
				/>
			</g></g
		></svg
	>
</div>
