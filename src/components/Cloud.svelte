<script>
  import Animation from './Animation.svelte';
  
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

  <div class="text2-container" class:show={showSecond}>
    <Animation text={displayText2} key={secondKey} />
  </div>
</div>

<style>
  .container {
    position: relative;
    width: 400px;
    height: 200px;  /* Add fixed height */
  }

  .text1-container, .text2-container {
    position: absolute;
    width: 100%;
    left: 0;
    transition: all 0.3s ease;
  }

  .text1-container {
    top: 0;
  }

  .text2-container {
    top: 60px;  /* Fixed position from top */
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
</style>
