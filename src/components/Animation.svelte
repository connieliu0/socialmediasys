<script>
  export let text = "";
  export let key = 0;
  
  let displayText = "";
  const typeDelay = 50;

  async function typeText() {
    displayText = "";
    
    for (let i = 0; i < text.length; i++) {
      displayText = text.slice(0, i + 1);
      await new Promise(resolve => setTimeout(resolve, typeDelay));
    }
  }

  $: {
    if (text) {
      typeText();
    }
  }
</script>

<div class="text-container">
  <div class="content-wrapper" class:has-text={displayText}>
    <div class="blur-background"></div>
    <span class="text">{displayText}</span>
  </div>
</div>

<style>
  .text-container {
    width: 100%;
    min-height: 1.5em;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    padding: 2rem;
    box-sizing: border-box;
  }

  .content-wrapper {
    position: relative;
    display: inline-block;
    padding: 2rem 3rem;
  }

  .blur-background {
    position: absolute;
    inset: 0;
    border-radius: 118.519px;
    background: rgba(255, 255, 255, 0.95);
    filter: blur(30px);
    border-radius: 5rem;
    box-shadow: 
      0 0 10px 2px rgba(255, 255, 255, 0.05),
      inset 0 0 10px 2px rgba(255, 255, 255, 0.05);
    z-index: 1;
    opacity: 0;
    transition: opacity 0.3s ease;
  }

  .has-text .blur-background {
    opacity: 1;
  }

  .text-container .content-wrapper .text {
    white-space: pre-wrap;
    word-wrap: break-word;
    color: #155FF3;
    position: relative;
    z-index: 2;
    font-size: 1.5em;
    width: 100%;
    text-align: center;
  }

  @media (max-width: 768px) {
    .text-container .content-wrapper .text {
      font-size: 1em;
    }
    .text-container {
      padding: 1rem;
    }
  }
</style>
