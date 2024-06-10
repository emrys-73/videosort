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
    import GradientText from "$lib/components/typo/gradientText/gradientText.svelte";
    import Subheader from "$lib/components/typo/subheader/subheader.svelte";


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

    let subheader;
    let arrow;


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


    const getEmoji = (emojiContent) => {
        switch (emojiContent) {
            case '😂':
                return "url('/joy.png')";
            case '👌':
                return "url('/ok.png')";
            case '👀':
                return "url('/eyes.png')";
            case '🥰':
                return "url('/love.png')";
            case '💩':
                return "url('/poop.png')";
            default:
                return "url('/joy.png')";
        }
    }

</script>

{#if show}
<div
    transition:fade={{ delay: 300, duration: 1000 }}
    class="w-full h-full min-h-screen  flex flex-col justify-center items-center gap-4">
    <div class="w-full h-[95vh] justify-center items-center flex flex-col relative gap-4">
        <video class="absolute top-0 w-full h-full z-10 opacity-15" src="/hero2.mp4" type="video/mp4" muted autoplay loop playsinline disablepictureinpicture/>    
    <div class="py-4 px-6 z-50">
        <IntersectionObserver element={title} let:intersecting once={true}>
            <div bind:this={title}>
                {#if intersecting}
                    <div
                        transition:fade={{ delay: 200, duration: 1000 }}
                        >
                        <h1 class="scroll-m-20 {headerGradient ? gradient : 'text-main'} font-bold text-5xl lg:text-7xl text-center">
                            Automatic Footage Sorting and Labelling for Filmmakers and Content Creators
                        </h1>
                    </div>
                {/if}
            </div>
        </IntersectionObserver>
    </div>

    <div class="flex flex-row gap-2 justify-center items-center py-8 z-50">
        <div class="hidden">
            <Input placeholder="Enter your email" label="Email" class="min-w-[20vw]" />
        </div>
        <Button href="https://tally.so/r/3NVJ4j" slot="label" target="_blank" class="min-w-[20vw] hover:min-w-[30vw] transition-all duration-500 ease-in-out rounded-full border-[0.5px] border-main bg-transparent text-main lg:text-xl dark:hover:text-sec dark:hover:border-sec hover:bg-transparent px-6">Join the Waitlist</Button>
    </div>

    <div class="absolute bottom-6 dark:text-sec text-main breathe mb-16 sm:mb-0">
        Scroll to explore
    </div>

</div>


<div class="w-full h-[50vh] flex-col justify-center items-center flex">
    <IntersectionObserver element={subheader} let:intersecting once={false}>
        <div bind:this={subheader} class="w-full h-full flex">
            {#if intersecting}
                <div
                    transition:fly={{ delay: 400, duration: 1400, x: -1200, y: 0, opacity: 0.01, easing: quintOut }}
                    class="w-full flex flex-col justify-center items-center"
                    >
                    <div class="w-3/4 border-l-[12px] border-main h-auto flex flex-col gap-4 py-2">
                        <h2 class="text-2xl xl:text-6xl lg:text-7xl font-semibold text-main px-4">
                            "Labelling and sorting footage is the most boring thing in the world."
                        </h2>
                        <span class="text-sm italic text-main px-4 md:text-2xl">
                            - Every Filmmaker, every Content Creator, ever.
                        </span>
                    </div>
                </div>
            {/if}
        </div>
    </IntersectionObserver>
    
    <div class="flex flex-col gap-6 h-[80vh] justify-center items-center">
        <IntersectionObserver element={arrow} let:intersecting once={false}>
            <div bind:this={arrow} class="w-full h-full flex">
                {#if intersecting}
                    <div
                        transition:fly={{ delay: 200, duration: 1400, x: 0, y: 800, opacity: 0.01, easing: quintOut }}
                        class="flex flex-col gap-4 justify-center items-center"
                        >
                        <span class="text-main font-semibold text-xl">
                            Let's fix that
                        </span>
                        <img src="/ari.png" alt="arr" class="scale-75">
                    </div>
                {/if}
            </div>
        </IntersectionObserver>
    </div>
</div>

<div class="w-full h-full min-h-screen justify-start items-center flex flex-col overflow-hidden py-2 md:py-20">
   <div class="lg:w-[90vw] xl:w-4/5 w-full px-6 h-full flex flex-col gap-6 justify-center items-center">
        <!-- First row -->
        <div class="w-full h-full flex lg:flex-row flex-col gap-6">
            
            <div class="w-full md:min-h-[55vh] min-h-[45vh]">
                <IntersectionObserver element={f1} let:intersecting>
                    <div bind:this={f1} class="w-full h-full">
                      {#if intersecting}
                      <div
                      transition:fade={{ delay: 0, duration: 1400, x: -1200, y: 0, opacity: 0.01, easing: quintOut }}
                      class="w-full md:h-[55vh] h-[45vh]"
                        >
                        <div class="w-full h-full dark:bg-myGray bg-myLightGray rounded-3xl flex flex-col justify-center items-center p-6 py-10 lg:py-6">
                            <Subheader size="sm">
                                Automatically
                            </Subheader>
                            <GradientText size="md">Sort and Label</GradientText>
                            <div class="md:w-3/4 w-full flex flex-col gap-4 justify-center items-start py-4 transition-all duration-500 ease-in-out">
                                <div class="flex">
                                    <div class="bg-main text-sec font-semibold rounded-full px-4 py-1 drop-shadow-md">
                                        03:16 Crowd Cheering
                                    </div>
                                </div>
                                <div class="flex flex-row w-full gap-2 justify-center">
                                    <div class="bg-main text-sec font-semibold rounded-full px-4 py-1 drop-shadow-md">
                                        02:42 Bread
                                    </div>
                                    <div class="bg-main text-sec font-semibold rounded-full px-4 py-1 drop-shadow-md">
                                        41:10 Hands
                                    </div>
                                </div>
                                <div class="flex w-full justify-end">
                                    <div class="bg-main text-sec font-semibold rounded-full px-4 py-1 drop-shadow-md">
                                        04:12 Boxing Gloves
                                    </div>
                                </div>
                            </div>
                            <Subheader>
                                *tailored to your workflow
                            </Subheader>
                        </div>
                      </div>
                      {/if}
                    </div>
                  </IntersectionObserver>
            </div>
            

            <div class="w-full h-[55vh] flex flex-col gap-6">
                <IntersectionObserver element={f2} let:intersecting>
                    <div bind:this={f2}
                        class="w-full h-full">
                        {#if intersecting}
                            <div
                            transition:fade={{ delay: 0, duration: 1400, x: 800, y: 0, opacity: 0.01, easing: quintOut }}
                                class="w-full flex flex-col gap-6 h-full">
                                <div 
                                    
                                    class="w-full h-auto dark:bg-myGray bg-myLightGray rounded-3xl min-h-[25vh] justify-center items-center flex-col p-6 flex transition-all duration-500 ease-in-out gap-1">
            
                                    <GradientText size="md">
                                        Find any clip you are looking for in seconds
                                    </GradientText>

                                    <Subheader>
                                        via searchable footage transcripts and categories
                                    </Subheader>
                                    
                                </div>

                                <div class="w-full h-full min-h-[25vh] flex flex-row gap-6">
                                    <div class="w-full h-full dark:bg-myGray bg-myLightGray rounded-3xl min-h-[20vh] justify-center items-center gap-4 flex flex-col">

                                        <Subheader>
                                            Customise tags and categories
                                        </Subheader>
                    
                                        <div class="flex flex-row w-full justify-center gap-1 md:gap-2 lg:gap-4">
                                            {#each tags as tag}
                                                <ToggleConfetti toggleOnce relative={false}>
                                                    <Button slot="label"
                                                        class="rounded-full w-16 h-16 bg-main dark:hover:bg-main transition-all duration-500 ease-in-out dark:bg-[#292929] text-center flex justify-center items-center text-2xl xl:text-4xl"
                                                        >
                                                        {tag.content}
                                                    </Button>
                                                    
                                                    <div style="position: fixed; top: -50px; left: 0; height: 100vh; width: 100vw; display: flex; justify-content: center; overflow: hidden;">
                                                        <Confetti x={[-5, 5]} y={[0, 0.1]} size=30 colorArray={[`${getEmoji(tag.content)}`]} delay={[50, 4000]}  duration=3000 amount=200 fallDistance="100vh" />
                                                    </div>
                                                </ToggleConfetti>
                                            {/each}
                                        </div>
                                    </div>
                                </div> 
                            </div>
                        {/if}
                    </div>
                </IntersectionObserver>
            </div>
        </div>

        <!-- Third row -->
        <div class="w-full min-h-[15vh] flex-row gap-6 flex">
            <IntersectionObserver element={f3} let:intersecting once={false}>
                <div bind:this={f3} class="w-full h-full">
                    {#if intersecting}
                        <div
                            transition:fade={{ delay: 0, duration: 1400, x: 0, y: -800, opacity: 0.01, easing: quintOut }}
                            class="w-full"
                                >
                            <div class="w-full h-full min-h-[15vh] rounded-3xl dark:bg-myGray bg-myLightGray flex flex-row justify-center items-center p-6 gap-6">
                                <GradientText size="lg">
                                    Label 10 Hours of Footage in 10 Minutes
                                </GradientText>
                                <!-- <h4 class=" font-semibold tracking-wider text-main dark:text-main text-lg md:text-xl lg:text-2xl xl:text-3xl">
                                    Faster than manual labelling
                                    <br>
                                    and with higher accuracy
                                </h4> -->
                            </div>
                        </div>
                    {/if}
                </div>
            </IntersectionObserver>
        </div>

        <!-- Fifth Row -->
        <div class="w-full h-full gap-6 flex min-h-[50vh] md:min-h-[25vh]">
            <IntersectionObserver element={f6} let:intersecting once={true}>
                <div bind:this={f6} class="w-full h-full">
                    {#if intersecting}
                        <div
                            transition:fade={{ delay: 0, duration: 1400, x: 0, y: -800, opacity: 0.01, easing: quintOut }}
                            class="w-full h-full flex flex-col-reverse md:flex-row gap-6"
                            >
                            <div class="w-full h-auto rounded-3xl dark:bg-myGray bg-myLightGray flex flex-col justify-center items-center p-6 lg:px-8 relative">
                                <div class="absolute bg-main rounded-full px-6 py-1 text-sec font-semibold -top-2 -left-2 text-sm">
                                    Coming soon
                                </div>
                                <Subheader>
                                    Generative AI agents use your briefings achieving
                                </Subheader>

                                <GradientText>
                                    Automatic rough cuts <br> in seconds
                                </GradientText>
                
                            </div>
                            <div class="md:w-[40vw] w-full h-full min-h-[25vh] rounded-3xl dark:bg-myGray bg-myLightGray flex flex-col justify-center items-center p-6 gap-6">
                                <Subheader>
                                    Seamless integrations with
                                </Subheader>

                                <div class="flex flex-row w-full h-full justify-center xl:gap-8 gap-2 lg:gap-6">
                                    <a href="https://www.blackmagicdesign.com/products/davinciresolve">
                                    <img src="/davinci.png" alt="DaVinci" class="scale-75 lg:scale-100 hover:scale-95 lg:hover:scale-110 transition-all duration-500 ease-in-out">
                                    </a>
                                    <a href="https://www.adobe.com/products/premiere.html">
                                        <img src="/premiere.png" alt="Premiere" class="scale-75 lg:scale-100 hover:scale-95 lg:hover:scale-110 transition-all duration-500 ease-in-out">
                                    </a>
                                    <a href="https://www.apple.com/final-cut-pro/">
                                        <img src="/finalcut.png" alt="Final Cut" class="scale-75 lg:scale-100 hover:scale-95 lg:hover:scale-110 transition-all duration-500 ease-in-out">
                                    </a>
                                </div>
                            </div>
                        </div>
                    {/if}
                </div>
            </IntersectionObserver>
        </div>
   </div>
</div>

    <div class="w-full flex flex-col text-center justify-center items-center h-[100vh] px-6 gap-4 relative">
        <img class="absolute top-0 w-full h-full z-10 opacity-15 object-cover" src="/bg.gif" alt="bg"  muted autoplay loop playsinline disablepictureinpicture/>
        <IntersectionObserver element={bottom} let:intersecting once={true}>
            <div bind:this={bottom} class="w-full flex justify-center items-center z-30">
                {#if intersecting}
                    <div
                        transition:fade={{ delay: 300, duration: 1000 }}
                        class="md:w-3/4 ">
                        <span class="md:w-3/5 w-full text-center text-xl md:text-2xl lg:text-3xl font-medium text-main dark:text-main">
                            We believe that the future of software should allow creators to focus less on tedious tasks and more on telling great stories. Our first step: Labelling and sorting footage is one of the most boring things in the world. This automates that.
                        </span>
                    </div>
                {/if}
            </div>
        </IntersectionObserver>
        <Button href="https://tally.so/r/3NVJ4j" slot="label" target="_blank" class="min-w-[20vw] hover:min-w-[30vw] transition-all duration-500 ease-in-out rounded-full border-[0.5px] border-main bg-transparent text-main lg:text-xl dark:hover:text-sec dark:hover:border-sec hover:bg-transparent px-6">Join the Waitlist</Button>
    </div>
</div>
{/if}