<script lang="ts">
	import { Input } from '$lib/components/ui/input/index.js';
	import { Button } from '$lib/components/ui/button/index.js';
	import { Label } from '$lib/components/ui/label/index.js';
	import Mail from 'lucide-svelte/icons/mail';
	import { Textarea } from '$lib/components/ui/textarea/index.js';
	import { cn } from '$lib/utils/cn';
	import Instagram from 'lucide-svelte/icons/instagram';
	import Linkedin from 'lucide-svelte/icons/linkedin';

	let typingMail = $state(false);
	let typingName = $state(false);
	let typingMessage = $state(false);
</script>

<div class="relative h-full w-full p-20">
	<div class="m-auto flex h-full flex-col items-center justify-center gap-3">
		<div class="flex h-full w-full flex-col items-center justify-center gap-10 2xl:w-1/2">
			<div class="text-center text-5xl font-bold 2xl:p-0">
				<span class="font-black text-[#74a49d]">Contactez-moi!</span>
			</div>
			<div class="flex flex-row items-center justify-center gap-6">
				<a href="https://www.instagram.com/mathildeguerei/" target="_blank"
					><Instagram class="h-10 w-10 hover:text-[#74a49d]" /></a
				>
				<a href="https://www.linkedin.com/in/mathilde-guer-6089b91b9/" target="_blank"
					><Linkedin class="h-10 w-10 hover:text-[#74a49d]" /></a
				>
			</div>
			<div class="w-1/2 border-b-4 border-[#74a49d] 2xl:w-1/4"></div>
			<form
				class="flex w-full flex-col items-center gap-6"
				action="https://api.web3forms.com/submit"
				method="POST"
			>
				<input type="hidden" name="access_key" value="be70568c-8ec8-4e56-b91a-ff7ed0054c7e" />
				<div
					class="flex w-full grow flex-col items-start justify-start gap-6 2xl:flex-row 2xl:gap-20"
				>
					<div class="flex w-full flex-col gap-1.5">
						<Label
							class={cn('text-lg font-semibold 2xl:text-2xl', typingName ? 'text-[#74a49d]' : '')}
							>Nom</Label
						>
						<Input
							class="focus:ring-none placeholder:lg rounded-none border-0 border-b-4 border-gray-300 p-0 text-sm focus:border-[#74a49d] 2xl:text-2xl 2xl:placeholder:text-2xl"
							type="text"
							name="name"
							required
							onfocus={() => {
								typingName = true;
							}}
							onblur={() => {
								typingName = false;
							}}
						/>
					</div>
					<div class="flex w-full flex-col gap-1.5">
						<Label
							class={cn('text-lg font-semibold 2xl:text-2xl', typingMail ? 'text-[#74a49d]' : '')}
							>Email</Label
						>
						<Input
							class="focus:ring-none rounded-none border-0 border-b-4 border-gray-300 p-0 text-sm placeholder:text-lg focus:border-[#74a49d] 2xl:text-2xl 2xl:placeholder:text-2xl"
							type="email"
							name="email"
							required
							onfocus={() => {
								typingMail = true;
							}}
							onblur={() => {
								typingMail = false;
							}}
						/>
					</div>
				</div>
				<div class="flex w-full flex-col gap-1.5 text-2xl">
					<Label
						class={cn('text-lg font-semibold 2xl:text-2xl', typingMessage ? 'text-[#74a49d]' : '')}
						>Message</Label
					>
					<Textarea
						class="focus:ring-none rounded-none border-0 border-b-4 border-gray-300 p-0 text-sm placeholder:text-lg focus:border-[#74a49d] 2xl:text-2xl 2xl:placeholder:text-2xl"
						name="message"
						required
						onfocus={() => {
							typingMessage = true;
						}}
						onblur={() => {
							typingMessage = false;
						}}
					/>
				</div>
				<Input type="hidden" name="redirect" value="https://web3forms.com/success" />
				<Button type="submit" class="w-fit hover:bg-[#74a49d]"
					><Mail class="mr-2 size-4 " />Envoyer</Button
				>
			</form>
		</div>
	</div>
</div>
