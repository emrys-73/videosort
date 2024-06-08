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
    <div class="w-full h-[100vh] justify-center items-center flex flex-col relative">
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
        <Button href="https://tally.so/r/3NVJ4j" slot="label" target="_blank" class="w-[20vw] hover:w-[30vw] transition-all duration-500 ease-in-out rounded-full border-[0.5px] border-main bg-transparent text-main text-xl hover:text-white hover:border-white hover:bg-transparent">Join Waitlist</Button>
    </div>

    <div class="absolute bottom-6 dark:text-white breathe">
        Scroll to explore
    </div>

</div>

<div class="w-full h-full min-h-screen justify-start items-center flex flex-col py-20">
   <div class="w-4/5 h-full flex flex-col gap-6 justify-center items-center">
        <!-- First row -->
        <div class="w-full h-full flex flex-row gap-6">
            <div class="w-full h-auto bg-[#161617] rounded-3xl flex flex-col justify-center items-center p-6">
                <h4 class="w-full text-center items-center text-white">
                    AI-Powered
                </h4>
                <h3 class="bg-gradient-to-r from-[#F2698D] to-[#D72655] text-transparent bg-clip-text text-6xl font-semibold py-2 text-center">
                    Sorting and Labelling
                </h3>
                <img src="/verses.png" alt="tags" class="pt-20">
            </div>
            <div class="w-full h-full flex flex-col gap-6">
                <div class="w-full h-full bg-[#161617] rounded-3xl min-h-[25vh] justify-center items-center p-6 flex">
                    <h3 class="bg-gradient-to-r from-[#F2698D] to-[#D72655] inline-block text-transparent bg-clip-text text-6xl font-semibold h-full w-full py-2 text-center">
                        Industry-leading AI video indexing engine
                    </h3>
                </div>
                <div class="w-full h-full  min-h-[30vh] flex flex-row gap-6">
                    <div class="bg-[#161617] rounded-3xl w-full h-auto flex flex-col justify-center items-center p-6">
                        <h4 class="w-full text-center items-center text-white">
                            Auto-generated
                        </h4>
                        <h3 class="bg-gradient-to-r from-[#F2698D] to-[#D72655] text-transparent bg-clip-text text-6xl font-semibold py-2 text-center">
                            Searchable Databse
                        </h3>
                    </div>
                    <div class="bg-[#161617] rounded-3xl w-full h-auto flex flex-col justify-center items-center gap-6">
                        <h3 class="text-8xl text-center items-center flex justify-center">
                            🙋‍♂️
                        </h3>
                        <h4 class="w-full text-center items-center text-white">
                            Face Recognition
                        </h4>
                    </div>
                </div>
            </div>
        </div>

        <!-- Second row -->
        <div class="w-full h-full flex flex-row gap-6 ">
            <div class="w-full flex flex-col gap-6">
                <div class="w-full h-auto bg-[#161617] rounded-3xl min-h-[30vh] flex flex-col gap-2 justify-center items-center ">
                    <h4 class="w-full text-center items-center text-white">
                        Up to
                    </h4>

                    <h3 class="bg-gradient-to-r from-[#F2698D] to-[#D72655] text-transparent bg-clip-text text-8xl font-semibold py-2 text-center">
                        94%
                    </h3>

                    <h4 class="w-full text-center items-center text-white">
                        faster than manual labelling
                    </h4>
                </div>

                <div class="w-full h-auto bg-[#161617] rounded-3xl min-h-[30vh] flex flex-col gap-6 justify-center items-center p-6">
                    <h3 class="text-8xl text-center items-center flex justify-center">
                        😋✌️
                    </h3>
                    <h4 class="w-full text-center items-center text-white">
                        Emotion Detection
                    </h4>
                </div>
            </div>
            <div class="w-full min-w-[60vw] h-auto rounded-3xl bg-[#161617] flex flex-col justify-center items-center relative">
                <img src="/macmock.png" alt="mac" class="h-2/3 absolute z-40">
                <div class="w-[33.5vw] h-[34vh] absolute z-50 min-h-80 bg-red-500 rounded-2xl mb-10">
                    <!-- svelte-ignore a11y-missing-attribute -->
                    <iframe src="/" frameborder="0"
                        class="w-full h-full"
                        />
                </div>
            </div>
        </div>

        <!-- Third row -->
        <div class="w-full h-full flex flex-row gap-6">
            <div class="w-full h-full min-h-[20vh] rounded-3xl bg-[#161617]">

            </div>
        </div>

        <!-- Fourth row -->
        <div class="w-full h-full flex flex-row gap-6">
            <div class="w-full h-full min-h-[60vh] flex flex-col gap-6">
                <div class="w-full h-full bg-[#161617] rounded-3xl min-h-[40vh]">

                </div>
                <div class="w-full h-full bg-[#161617] rounded-3xl min-h-[25vh]">

                </div>
            </div>
            <div class="w-full h-full min-h-[60vh] flex flex-col gap-6">
                <div class="w-full h-full bg-[#161617] rounded-3xl min-h-[35vh]">

                </div>
                <div class="w-full h-full bg-[#161617] rounded-3xl min-h-[30vh]">

                </div>
            </div>
        </div>


   </div>
</div>

    <!-- <div class=" w-full sm:w-3/4 md:w-3/5 justify-center items-center">
        <div class="font-bold px-4 py-4 flex flex-col justify-center items-center text-center border-[1px] rounded-xl drop-shadow-lg">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque cursus arcu eget urna iaculis, nec tempus urna dapibus. Curabitur at ex felis.
        </div>
    </div> -->

    <div class="w-full min-h-[70vh] h-full justify-start items-center flex flex-col py-20">
        <div class="w-full justify-start items-start flex px-8 lg:w-2/3">
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

        <IntersectionObserver element={features} let:intersecting once={true}>
            <div bind:this={features}>
                {#if intersecting}
                <div
                transition:fade={{ delay: 300, duration: 800 }}
                  >
                  <img src="/lg_bento_i.png" alt="bento" class="dark:hidden block">
                  <img src="/n_bg_lg.png" alt="bento" class="hidden dark:block">
                </div>
                {/if}
              </div>
        
        </IntersectionObserver>
        
        <div class="w-full lg:w-2/3 flex flex-col">

        </div>

    </div>

    <div class="w-full flex flex-col text-center justify-center items-center py-16">
        <span class="md:w-3/5 w-full text-center text-3xl font-medium text-white">
            Simplify Your Workflow, Maximize Your Creativity. Effortlessly Manage and Organize Large Video Footage Volumes with AI-Powered Automation that sorts and labels your video footage for you.
        </span>
    </div>


    <div class="w-full min-h-[90vh] h-full flex flex-col justify-center items-center gap-4">

        <a href="https://tally.so/r/3NVJ4j" target="_blank" class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl text-center hover:text-white transition-all duration-500 ease-in-out">
            Launching Soon
        </a>

        <!-- <Button href="https://tally.so/r/3NVJ4j" slot="label" target="_blank" class="w-[20vw] rounded-full border-[0.5px] border-main bg-transparent text-main text-xl hover:text-white hover:border-white hover:bg-transparent">Join Waitlist</Button> -->
    </div>

</div>
{/if}