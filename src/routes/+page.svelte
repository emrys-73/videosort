<script>
// @ts-nocheck

    import { Confetti } from "svelte-confetti"
    import ToggleConfetti from "../lib/confetti/ToggleConfetti.svelte";
    import ConfettiOnClick from "../lib/confetti/ConfettiOnClick.svelte";
    import Button from "$lib/components/ui/button/button.svelte";
    import Input from "$lib/components/ui/input/input.svelte";
    import * as Card from "$lib/components/ui/card";
    // import TypewriterEffectSmooth from "$lib/components/ui/TypewriterEffect/TypewriterEffectSmooth.svelte";
    import { fade, slide, scale, fly, blur } from 'svelte/transition';
    import { quintOut, cubicInOut, quintInOut } from 'svelte/easing';
    import IntersectionObserver from "svelte-intersection-observer";
    import { onMount } from "svelte";


    let show;
    $: show = false;


    onMount(() => {
        show = true;
    });

    const words = [
		{
			text: 'Build'
		},
		{
			text: 'awesome'
		},
		{
			text: 'apps'
		},
		{
			text: 'with'
		},
		{
			text: 'Aceternity.',
			className: 'text-blue-500 dark:text-blue-500'
		}
	];


    let maincta;

    let features;


</script>

{#if show}
<div
    transition:fade={{ delay: 300, duration: 1000 }}
    class="w-full h-full min-h-screen  flex flex-col justify-center items-center gap-4">
    <div class="w-full h-[90vh] justify-center items-center flex flex-col">
        <!-- <video class="absolute w-full h-full object-cover z-0" muted autoplay loop playsinline disablepictureinpicture>
			<source src="https://www.youtube.com/watch?v=OOnECHfc6RQ" type="video/mp4" />
		</video> -->

    
    <div class="py-4">
        <h1 class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl text-center">
            AI-Driven Footage Sorting <br>
            for Film Makers and Content Creators
        </h1>
        
    </div>

    <div class="flex flex-row gap-2 justify-center items-center">
        <div class="hidden">
            <Input placeholder="Enter your email" label="Email" class="min-w-[20vw]" />
        </div>

        <!-- <ToggleConfetti toggleOnce relative={false}>
            <Button href="https://tally.so/r/3NVJ4j" slot="label" class="w-[20vw] rounded-full">Join Waitlist</Button>
        
            <div style="position: fixed; top: -50px; left: 0; height: 100vh; width: 100vw; display: flex; justify-content: center; overflow: hidden;">
                <Confetti x={[-5, 5]} y={[0, 0.1]} delay={[500, 2000]}  infinite duration=5000 amount=200 fallDistance="100vh" />
            </div>
        </ToggleConfetti> -->
        <Button href="https://tally.so/r/3NVJ4j" slot="label" class="w-[20vw] rounded-full border-[0.5px] border-[#c53ab0] bg-transparent text-[#c53ab0] text-xl ">Join Waitlist</Button>
    </div>

</div>

    <!-- <div class=" w-full sm:w-3/4 md:w-3/5 justify-center items-center">
        <div class="font-bold px-4 py-4 flex flex-col justify-center items-center text-center border-[1px] rounded-xl drop-shadow-lg">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque cursus arcu eget urna iaculis, nec tempus urna dapibus. Curabitur at ex felis.
        </div>
    </div> -->

    <div class="w-full bg-[#9140EF] dark:bg-[#161617] flex flex-col text-center justify-center items-center py-16">
        <span class="md:w-3/5 w-full text-center text-3xl font-medium text-white">
            Simplify Your Workflow, Maximize Your Creativity. Effortlessly Manage and Organize Large Video Footage Volumes with AI-Powered Automation that sorts and labels your video footage for you.
        </span>
    </div>

    <div class="w-full min-h-[90vh] h-full justify-start items-center flex flex-col ">
        <div class="w-full justify-start items-start flex px-8 lg:w-2/3 py-20 lg:py-40">
            <IntersectionObserver element={maincta} let:intersecting>
                <div bind:this={maincta}>
                  {#if intersecting}
                  <div
                  transition:fade={{ delay: 0, duration: 2000 }}
                    >
                    <h2 class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl text-center hidden">
                        Features
                    </h2>
                  </div>
                  {/if}
                </div>
              </IntersectionObserver>
        </div>

        <IntersectionObserver element={features} let:intersecting>
            <div bind:this={features}>
                {#if intersecting}
                <div
                transition:fade={{ delay: 300, duration: 800 }}
                  >
                  <img src="/lg_bento_i.png" alt="bento" class="dark:hidden block">
                  <img src="/p_lg_vs.png" alt="bento" class="hidden dark:block">
                </div>
                {/if}
              </div>
        
        </IntersectionObserver>
        
        <div class="w-full lg:w-2/3 flex flex-col">

        </div>

    </div>


    <div class="w-full min-h-[90vh] h-full flex flex-col justify-center items-center gap-4">

        <h2 class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl text-center">
            Launching Soon
        </h2>

        <Button href="https://tally.so/r/3NVJ4j" slot="label" class="w-[20vw] rounded-full">Join Waitlist</Button>
    </div>

</div>
{/if}