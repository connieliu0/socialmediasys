<script>
  export let text1 = "";
  export let text2 = "";
  export let key = 0; // Add this to force re-render
  
  let displayText1 = "";
  let displayText2 = "";
  let isFirstDone = false;
  
  const typeDelay = 50; // milliseconds between each character

  async function typeText() {
    displayText1 = "";
    displayText2 = "";
    isFirstDone = false;
    
    // Type first text
    for (let i = 0; i < text1.length; i++) {
      displayText1 = text1.slice(0, i + 1);
      await new Promise(resolve => setTimeout(resolve, typeDelay));
    }
    
    await new Promise(resolve => setTimeout(resolve, 300));
    isFirstDone = true;

    // Type second text
    for (let i = 0; i < text2.length; i++) {
      displayText2 = text2.slice(0, i + 1);
      await new Promise(resolve => setTimeout(resolve, typeDelay));
    }
  }

  $: {
    if (text1 && text2) {
      typeText();
    }
  }
</script>

<div class="container">
  <div class="text-wrapper">
    <span class="text1" class:shrink={isFirstDone}>{displayText1}</span>
    <span class="text2">{displayText2}</span>
  </div>
</div>

<style>
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .text-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
  }

  .text1 {
    transition: transform 0.3s ease, font-size 0.3s ease, opacity 0.3s ease;
  }

  .text1.shrink {
    transform: translateY(-10px);
    font-size: 0.8em;
    opacity: 0.7;
  }

  .text2 {
    font-weight: bold;
  }
</style>
