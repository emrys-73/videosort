<script>
	import '../app.css';
	import { ModeWatcher, setMode } from "mode-watcher";
	import Sun from "svelte-radix/Sun.svelte";
  	import Moon from "svelte-radix/Moon.svelte";
  	import { toggleMode } from "mode-watcher";
  	import Button from '$lib/components/ui/button/button.svelte';
	import { onMount } from 'svelte';

	onMount(() => {
		setMode("dark");
	})

</script>

<ModeWatcher />

<div class="w-full h-full min-h-screen flex flex-col justify-center items-center relative dark:bg-myBlack bg-sec ">
	<div class="fixed top-0 h-[5vh] w-full flex flex-row justify-between px-6 items-center backdrop-blur-md z-50">
		<div class="font-black text-lg uppercase dark:text-main text-main ">
			Avlana
		</div>

		<div class="hidden">
			<Button on:click={toggleMode} variant="outline" size="icon">
				<Sun
				  class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0 dark:text-sec text-main"
				/>
				<Moon
				  class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100 dark:text-sec text-main"
				/>
			  </Button>
		</div>
	</div>

	<div class="w-full h-full ">
		<slot/>
	</div>

	<div class="w-full absolute bottom-0 h-16 dark:bg-transparent  text-main dark:text-secc bg-myLightGray justify-between items-center px-8 py-2 flex flex-row backdrop-blur-md z-50">
		<div>
			All rights reserved
		</div>

		<div class="font-black text-lg uppercase ">
			Avlana
		</div>
	</div>


</div>

