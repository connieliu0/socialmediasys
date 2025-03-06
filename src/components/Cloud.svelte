<script>
  import Animation from './Animation.svelte';
  import { createEventDispatcher } from 'svelte';
  
  const dispatch = createEventDispatcher();
  
  export let text1 = "";
  export let text2 = "";
  export let key = 0;
  
  let isFirstDone = false;
  let showSecond = false;
  let firstKey = 0;
  let secondKey = 0;
  let displayText2 = "";

  async function startSequence() {
    isFirstDone = false;
    showSecond = false;
    displayText2 = "";
    firstKey = key;
    secondKey = key;
    
    await new Promise(resolve => 
      setTimeout(resolve, (text1.length * 50) + 200)
    );
    
    showSecond = true;
    isFirstDone = true;
    displayText2 = text2;

    // Wait for second text to complete
    await new Promise(resolve => 
      setTimeout(resolve, (text2.length * 50) + 200)
    );

    dispatch('complete');
  }

  $: {
    if (text1 && text2) {
      startSequence();
    }
  }
</script>

<div class="container">
  <div class="text1-container" class:shrink={isFirstDone}>
    <Animation text={text1} key={firstKey} />
  </div>
</div>

<div class="text2-container" class:show={showSecond}>
  <Animation text={displayText2} key={secondKey} />
</div>

<style>
  .container {
    position: relative;
    width: 100%;
    height: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .text1-container, .text2-container {
    position: relative;
    width: 100%;
    max-width: 800px;
    margin: 0 auto;
    text-align: center;
    transition: all 0.3s ease;
  }

  .text2-container {
    opacity: 0;
    transform: translateY(20px);
  }

  .text2-container.show {
    opacity: 1;
    transform: translateY(0);
  }

  .text1-container.shrink {
    transform: translateY(-20px) scale(0.8);
    opacity: 0.7;
  }

  :global(.animation-text) {
    word-wrap: break-word;
    white-space: pre-wrap;
  }
</style>
