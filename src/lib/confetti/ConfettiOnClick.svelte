<script>
// @ts-nocheck

    import { Confetti } from "svelte-confetti"
  
    const duration = 2000
  
    let things = []
    let timeout
  
    async function moveConfetti(event) {
      const { target, clientX, clientY } = event
  
      const elementY = target.getBoundingClientRect().top
      const elementX = target.getBoundingClientRect().left
  
      const x = clientX - elementX
      const y = clientY - elementY
  
      things = [...things, { x, y }]
  
      clearTimeout(timeout)
  
      timeout = setTimeout(() => things = [], duration)
    }
  </script>
  
  
  
  <!-- svelte-ignore a11y-no-static-element-interactions -->
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div class="box" on:click={moveConfetti}>
    <span>Click in me</span>
  
    {#each things as thing}
      <div class="mover" style="left: {thing.x}px; top: {thing.y}px">
        <Confetti y={[-0.5, 0.5]} fallDistance=20px amount=10 {duration} />
      </div>
    {/each}
  </div>
  
  
  
  <style>
    .box {
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
      height: 10rem;
      width: 100%;
          border: 1px solid lightgray;
          border-radius: 0.5rem;
      background: white;
      user-select: none;
    }
  
    .mover {
      position: absolute;
    }
  
    span {
      pointer-events: none;
    }
  </style>
  