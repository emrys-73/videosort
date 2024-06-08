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

    let gradient = "bg-gradient-to-r from-sec to-main text-transparent bg-clip-text text-4xl xl:text-5xl"

    let gradientBig = "bg-gradient-to-r from-sec to-main text-transparent bg-clip-text text-6xl md:text-8xl "

    let gradientSmall = "bg-gradient-to-r from-sec to-main text-transparent bg-clip-text text-xl lg:text-3xl"

    let maincta;

    let features;


    let f1;
    let f2;
    let f3;
    let f4;
    let f5;
    let f6;
    let f7;
    let f8;


    let title;
    let bottom;

    let headerGradient = false;

    const tags = [
        {
            tag: "Smile",
            content: '😂',
        },
        {
            tag: "Bravo",
            content: '👌',
        },
        {
            tag: "Eyes",
            content: '👀',
        },
        {
            tag: "Love",
            content: '🥰',
        },
        {
            tag: "Caca",
            content: '💩',
        },
    ]

</script>

{#if show}
<div
    transition:fade={{ delay: 300, duration: 1000 }}
    class="w-full h-full min-h-screen  flex flex-col justify-center items-center gap-4">
    <div class="w-full h-[100vh] justify-center items-center flex flex-col relative">
        <!-- <video class="absolute w-full h-full object-cover z-0" muted autoplay loop playsinline disablepictureinpicture>
			<source src="https://www.youtube.com/watch?v=OOnECHfc6RQ" type="video/mp4" />
		</video> -->

    
    <div class="py-4 px-6">
        <IntersectionObserver element={title} let:intersecting once={false}>
            <div bind:this={title}>
                {#if intersecting}
                    <div
                        transition:fade={{ delay: 200, duration: 1000 }}
                        >
                        <h1 class="scroll-m-20 {headerGradient ? gradient : 'text-main'} font-bold text-5xl lg:text-7xl text-center">
                            AI-Driven Footage Sorting <br>
                            for Film Makers and Content Creators
                        </h1>
                    </div>
                {/if}
            </div>
        </IntersectionObserver>
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
        <Button href="https://tally.so/r/3NVJ4j" slot="label" target="_blank" class="min-w-[20vw] hover:min-w-[30vw] transition-all duration-500 ease-in-out rounded-full border-[0.5px] border-main bg-transparent text-main lg:text-xl hover:text-sec hover:border-sec hover:bg-transparent px-6">Join Waitlist</Button>
    </div>

    <div class="absolute bottom-6 dark:text-sec text-main breathe">
        Scroll to explore
    </div>

</div>

<div class="w-full h-full min-h-screen justify-start items-center flex flex-col overflow-hidden">
   <div class="lg:w-4/5 w-full px-6 h-full flex flex-col gap-6 justify-center items-center">
        <!-- First row -->
        <div class="w-full h-full flex lg:flex-row flex-col gap-6">
            
            <div class="w-full">
                <IntersectionObserver element={f1} let:intersecting>
                    <div bind:this={f1}>
                      {#if intersecting}
                      <div
                      transition:fly={{ delay: 0, duration: 2000, x: -1200, y: 0, opacity: 0.01, easing: quintOut }}
                      class="w-full md:h-[50vh]"
                        >
                        <div class="w-full h-full dark:bg-myGray bg-myLightGray rounded-3xl flex flex-col justify-center items-center p-6 py-10 lg:py-6">
                            <h4 class="w-full text-center items-center dark:text-sec text-main font-semibold text-xl">
                                AI-Powered
                            </h4>
                            <h3 class="{gradient} text-transparent font-semibold py-2 text-center">
                                Sorting and Labelling
                            </h3>
                            <img src="/verses.png" alt="tags" class="pt-6">
                        </div>
                      </div>
                      {/if}
                    </div>
                  </IntersectionObserver>
            </div>
            

            <div class="w-full h-[50vh] flex flex-col gap-6">
                <IntersectionObserver element={f2} let:intersecting>
                    <div bind:this={f2}
                        class="w-full h-full">
                        {#if intersecting}

                        <div
                        transition:fly={{ delay: 0, duration: 2000, x: 1200, y: 0, opacity: 0.01, easing: quintOut }}
                            class="w-full flex flex-col gap-6 h-full">
                            <div 
                                
                                class="w-full h-auto dark:bg-myGray bg-myLightGray rounded-3xl min-h-[25vh] justify-center items-center flex-col p-6 flex transition-all duration-500 ease-in-out">
        
                                <h3 class="{gradient} justify-center items-center flex font-semibold h-full w-full py-2 text-center">
                                        Industry-leading AI video indexing engine
                                    </h3>
                            </div>

                            <div class="w-full h-full min-h-[20vh] flex flex-row gap-6">
                                <div class="dark:bg-myGray bg-myLightGray rounded-3xl w-full h-auto flex flex-col justify-center items-center p-6">
                                    <h4 class="w-full text-center items-center dark:text-sec text-main font-semibold text-xl">
                                        Auto-generated
                                    </h4>
                                    <h3 class="{gradient} font-semibold py-2 text-center">
                                        Database
                                    </h3>
                                </div>
                            <div class="dark:bg-myGray bg-myLightGray rounded-3xl w-full h-auto flex flex-col justify-center items-center gap-6 p-6">
                                <h3 class="text-4xl sm:text-5xl lg:text-6xl xl:text-8xl text-center items-center flex justify-center">
                                    🙋‍♂️
                                </h3>
                                <h4 class="w-full text-center items-center dark:text-sec text-main font-semibold text-xl">
                                    Face Recognition
                                </h4>
                            </div>
                        </div> 

                    </div>
                {/if}
                    </div>

                </IntersectionObserver>
            </div>
        </div>

        <!-- Second row -->
        <div class="w-full h-full hidden flex-row gap-6 ">
            
            <div class="w-full flex flex-col gap-6">
                <div class="w-full h-auto dark:bg-myGray bg-myLightGray rounded-3xl min-h-[30vh] flex flex-col gap-2 justify-center items-center p-6">
                    <h4 class="w-full text-center items-center dark:text-sec text-main font-semibold text-xl">
                        Up to
                    </h4>

                    <h3 class="{gradient} text-8xl font-semibold py-2 text-center">
                        94%
                    </h3>

                    <h4 class="w-full text-center items-center dark:text-sec text-main font-semibold text-lg md:text-xl">
                        faster than manual labelling
                    </h4>
                </div>

                <div class="w-full h-auto dark:bg-myGray bg-myLightGray rounded-3xl min-h-[30vh] flex flex-col gap-6 justify-center items-center p-6">
                    <h3 class="text-8xl text-center items-center flex justify-center">
                        😋✌️
                    </h3>
                    <h4 class="w-full text-center items-center dark:text-sec text-main font-semibold text-xl">
                        Emotion Detection
                    </h4>
                </div>
            </div>
            <div class="w-full min-w-[60vw] h-auto rounded-3xl dark:bg-myGray bg-myLightGray flex flex-col justify-center items-center relative">
                <img src="/macmock.png" alt="mac" class="h-2/3 absolute z-40">
                <div class="w-[33.5vw] h-[34vh] absolute z-50 min-h-80 dark:bg-myBlack bg-myWhite rounded-2xl mb-10">
                    <!-- svelte-ignore a11y-missing-attribute -->
                    <iframe src="/" frameborder="0" scrolling="no"
                        class="w-full h-full p-2 flex justify-center items-center"
                        />
                </div>
            </div>
        </div>

        <!-- Third row -->
        <div class="w-full h-full flex-row gap-6 flex">
            <IntersectionObserver element={f3} let:intersecting once={false}>
                <div bind:this={f3} class="w-full h-full">
                    {#if intersecting}
                        <div
                            transition:fly={{ delay: 0, duration: 2000, x: 0, y: -1200, opacity: 0.01, easing: quintOut }}
                            class="w-full"
                                >
                            <div class="w-full h-full min-h-[20vh] rounded-3xl dark:bg-myGray bg-myLightGray flex flex-row justify-center items-center p-6 gap-6">
                                <h3 class="{gradientBig} font-semibold py-2 text-center">
                                    94%
                                </h3>
                                <h4 class=" font-semibold tracking-wider text-main dark:text-main text-lg md:text-xl lg:text-2xl xl:text-3xl">
                                    Faster than manual labelling
                                    <br>
                                    and with higher accuracy
                                </h4>
                            </div>
                        </div>
                    {/if}
                </div>
            </IntersectionObserver>
        </div>

        <!-- Fourth row -->
        <div class="w-full h-full flex md:flex-row flex-col gap-6">
            <div class="w-full h-full min-h-[60vh] flex flex-col gap-6">
                <IntersectionObserver element={f4} let:intersecting once={false}>
                    <div bind:this={f4} class="w-full h-full">
                        {#if intersecting} 
                        <div
                            transition:fly={{ delay: 0, duration: 2000, x: -1200, y: 0, opacity: 0.01, easing: quintOut }}    
                            class="w-full h-full flex flex-col gap-6 ">
                            <div class="w-full h-full dark:bg-myGray bg-myLightGray rounded-3xl min-h-[40vh] justify-center items-center flex flex-col">
                                <h4 class="w-full text-center items-center {gradient} font-semibold text-xl">
                                    Seamless
                                </h4>
                                <h3 class="{gradient} font-semibold md:py-2 text-center">
                                    Integrations
                                </h3>
            
                                <div class="flex flex-row w-full h-full justify-center lg:gap-16 gap-6 py-6">
                                    <img src="/davinci.png" alt="DaVinci">
                                    <img src="/premiere.png" alt="Premiere">
                                    <img src="/finalcut.png" alt="Final Cut">
                                </div>
            
                            </div>
                            <div class="w-full h-full dark:bg-myGray bg-myLightGray rounded-3xl min-h-[25vh] justify-center items-center flex flex-col lg:p-8 p-6">
                                <h4 class="w-full text-center items-center dark:text-sec text-main font-semibold text-xl">
                                    Indexable
                                </h4>
            
                                <h3 class="{gradient} font-semibold py-2 text-center">
                                    Speech-To-Text Transcription
                                </h3>
            
                            </div>
                        </div>
                        {/if}
                    </div>
                </IntersectionObserver>
                
            </div>
            <div class="w-full h-full min-h-[60vh] flex flex-col gap-6">
                <IntersectionObserver element={f5} let:intersecting once={false}>
                    <div bind:this={f5} class="w-full h-full">
                        {#if intersecting} 
                            <div
                                transition:fly={{ delay: 0, duration: 2000, x: 1200, y: 0, opacity: 0.01, easing: quintOut }}    
                                class="w-full h-full flex flex-col gap-6"
                                >
                                <div class="w-full h-full dark:bg-myGray bg-myLightGray rounded-3xl min-h-[35vh] justify-center items-center gap-2 flex flex-col">

                                    <h4 class="w-full text-center items-center dark:text-sec text-main font-semibold text-xl">
                                        Customisable tags and categories
                                    </h4>
                
                                    <div class="flex flex-row w-full h-full justify-center gap-1 md:gap-2 lg:gap-4 py-8">
                                        {#each tags as tag}
                                            <div
                                                class="rounded-full w-16 h-16 lg:w-16 lg:h-16 bg-main dark:bg-[#292929] text-center flex justify-center items-center text-2xl xl:text-4xl"
                                                >
                                                {tag.content}
                                            </div>
                                        {/each}
                                    </div>
                
                                    <h4 class="w-full text-center items-center dark:text-sec text-main font-semibold text-xl">
                                        For better organisation
                                    </h4>
                
                                </div>
                                <div class="w-full h-full dark:bg-myGray bg-myLightGray rounded-3xl min-h-[30vh] justify-center items-center flex flex-col">
                                    <h4 class="w-full text-center items-center {gradientSmall} font-semibold">
                                        Process up to 
                                    </h4>
                    
                                    <h3 class="{gradient} font-semibold py-2 text-center">
                                        1.000.000
                                    </h3>
                
                                    <h4 class="w-full text-center items-center {gradientSmall} font-semibold">
                                        minutes of footage per year
                                    </h4>
                                </div>
                            </div>
                        {/if}
                    </div>
                </IntersectionObserver>
                
            </div>
        </div>

        <!-- Fifth Row -->
        <div class="w-full h-full flex-row gap-6 flex">
            <IntersectionObserver element={f6} let:intersecting once={false}>
                <div bind:this={f6} class="w-full h-full">
                    {#if intersecting}
                        <div
                            transition:fly={{ delay: 0, duration: 2000, x: 0, y: -1200, opacity: 0.01, easing: quintOut }}
                            >
                            <div class="w-full h-full min-h-[20vh] rounded-3xl dark:bg-myGray bg-myLightGray flex flex-col justify-center items-center p-6">
                                <h4 class="w-full text-center items-center {gradientSmall} font-semibold">
                                    Sell or find leftover shots through our
                                </h4>
                
                                <h3 class="{gradient} font-semibold py-2 text-center">
                                    Footage Marketplace
                                </h3>
                            </div>
                        </div>
                    {/if}
                </div>
            </IntersectionObserver>
            
        </div>


   </div>
</div>

    <!-- Hidden image -->
    <div class="w-full min-h-[70vh] h-full justify-start items-center flex-col py-20 hidden">
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
    

    </div>

    <div class="w-full flex flex-col text-center justify-center items-center min-h-[90vh] px-6 gap-4">
        <IntersectionObserver element={bottom} let:intersecting once={false}>
            <div bind:this={bottom} class="w-full flex justify-center items-center">
                {#if intersecting}
                    <div
                        transition:fade={{ delay: 300, duration: 1000 }}
                        class="md:w-3/4 ">
                        <span class="md:w-3/5 w-full text-center text-xl md:text-2xl lg:text-3xl font-medium text-main dark:text-main">
                            Simplify Your Workflow, Maximize Your Creativity. Effortlessly Manage and Organize Large Video Footage Volumes with AI-Powered Automation that sorts and labels your video footage for you.
                        </span>
                    </div>
                {/if}
            </div>
        </IntersectionObserver>
        <Button href="https://tally.so/r/3NVJ4j" slot="label" target="_blank" class="min-w-[20vw] hover:min-w-[30vw] transition-all duration-500 ease-in-out rounded-full border-[0.5px] border-main bg-transparent text-main lg:text-xl hover:text-sec hover:border-sec hover:bg-transparent px-6">Join Waitlist</Button>
    </div>


    <!-- Hidden Block -->
    <div class="w-full min-h-[90vh] h-full hidden flex-col justify-center items-center gap-4">

        <a href="https://tally.so/r/3NVJ4j" target="_blank" class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl text-main hover:text-sec dark:text-sec dark:hover:text-main text-center transition-all duration-500 ease-in-out">
            Launching Soon
        </a>

        <!-- <Button href="https://tally.so/r/3NVJ4j" slot="label" target="_blank" class="w-[20vw] rounded-full border-[0.5px] border-main bg-transparent text-main text-xl hover:text-white hover:border-white hover:bg-transparent">Join Waitlist</Button> -->
    </div>

</div>
{/if}