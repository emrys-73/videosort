<script>
	import '../app.css';
	import { ModeWatcher } from "mode-watcher";
	import Sun from "svelte-radix/Sun.svelte";
  	import Moon from "svelte-radix/Moon.svelte";
  	import { toggleMode } from "mode-watcher";
  	import Button from '$lib/components/ui/button/button.svelte';

</script>

<ModeWatcher />

<div class="w-full h-full min-h-screen flex flex-col justify-center items-center relative bg-[#F5F5F7] dark:bg-[#000] text-[#c53ab0]">
	<div class="fixed top-0 h-[5vh] w-full flex flex-row justify-between px-6 items-center backdrop-blur-md">
		<div class="font-black text-lg uppercase ">
			Videosort
		</div>

		<div>
			<Button on:click={toggleMode} variant="outline" size="icon">
				<Sun
				  class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0"
				/>
				<Moon
				  class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
				/>
			  </Button>
		</div>
	</div>

	<div class="w-full h-full ">
		<slot/>
	</div>

	<div class="w-full absolute bottom-0 h-16 bg-[#000000] text-white dark:text-white dark:bg-[#161617] justify-between items-center px-8 py-2 flex flex-row">
		<div>
			All rights reserved
		</div>

		<div class="font-black text-lg uppercase ">
			Videosort
		</div>
	</div>


</div>

