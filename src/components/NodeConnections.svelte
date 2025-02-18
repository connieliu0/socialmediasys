<script>
  import { onMount } from 'svelte';
  import { writable } from 'svelte/store';
  import Animation from './Animation.svelte';

  const columns = {
    persistence: ['10 seconds', '1 day', '1 week', 'forever'],
    media: ['short text', 'long text', 'image', 'video'],
    network: ['strangers of your interest', 'everyone you\'ve met', 'intimate'],
    limit: ['yes', 'no'],
    spread: ['yes', 'no']
  };

  const selectedNodes = writable({});
  const nodePositions = writable({});
  const output = writable('');

  let container;
  
  // Track the previous column for drawing lines
  let previousColumn = null;

  let outputText1 = '';
  let outputText2 = '';
  let animationKey = 0;

  onMount(() => {
    // Initialize node position tracking after components are mounted
    updateNodePositions();
    window.addEventListener('resize', updateNodePositions);
    return () => window.removeEventListener('resize', updateNodePositions);
  });

  function updateNodePositions() {
    const nodes = container.querySelectorAll('.node');
    const positions = {};
    
    nodes.forEach(node => {
      const rect = node.getBoundingClientRect();
      const containerRect = container.getBoundingClientRect();
      const columnName = node.dataset.column;
      const value = node.dataset.value;
      
      // Calculate positions relative to the container
      positions[`${columnName}-${value}`] = {
        x: rect.left - containerRect.left + rect.width / 2,
        y: rect.top - containerRect.top + rect.height / 2
      };
    });
    
    nodePositions.set(positions);
  }

  function selectNode(column, value, event) {
    selectedNodes.update(nodes => {
      const newNodes = { ...nodes, [column]: value };
      updateOutput(newNodes);
      return newNodes;
    });
    
    // Update positions after selection
    updateNodePositions();
  }

  function updateOutput(nodes) {
    if (nodes.persistence && nodes.media && nodes.network && nodes.limit && nodes.spread) {
      animationKey++;
      if (nodes.persistence === '10 seconds' && nodes.media === 'short text' && 
          nodes.network === 'strangers of your interest' && nodes.limit === 'yes' && 
          nodes.spread === 'yes') {
        outputText1 = 'connecting to the network';
        outputText2 = 'the birds are singing';
      } else if (nodes.persistence === 'forever' && nodes.media === 'video' && 
                 nodes.network === 'intimate' && nodes.limit === 'no' && 
                 nodes.spread === 'no') {
        outputText1 = 'processing your choices';
        outputText2 = 'who you truly are crystallizes';
      } else {
        outputText1 = 'analyzing combination';
        outputText2 = 'different combination output';
      }
    }
  }

  function getLines() {
    const lines = [];
    const columnOrder = Object.keys(columns);
    let prevNode = null;

    columnOrder.forEach((column, index) => {
      const selectedValue = $selectedNodes[column];
      if (selectedValue) {
        const currentNodeKey = `${column}-${selectedValue}`;
        const currentPos = $nodePositions[currentNodeKey];

        if (prevNode && currentPos) {
          const prevPos = $nodePositions[prevNode];
          if (prevPos) {
            lines.push({
              x1: prevPos.x,
              y1: prevPos.y,
              x2: currentPos.x,
              y2: currentPos.y
            });
          }
        }
        prevNode = currentNodeKey;
      }
    });

    return lines;
  }
</script>

<div class="container" bind:this={container}>
  <!-- SVG overlay for lines -->
  <svg class="lines-overlay">
    {#each getLines() as line}
      <line
        x1={line.x1}
        y1={line.y1}
        x2={line.x2}
        y2={line.y2}
        stroke="white"
        stroke-width="2"
        stroke-dasharray="4,4"
      />
    {/each}
  </svg>

  {#each Object.entries(columns) as [column, values]}
    <div class="column">
      <h3>{column}</h3>
      {#each values as value}
        <button
          class="node"
          class:selected={$selectedNodes[column] === value}
          data-column={column}
          data-value={value}
          on:click={(e) => selectNode(column, value, e)}
        >
          {value}
        </button>
      {/each}
    </div>
  {/each}

  {#if outputText1 && outputText2}
    <div class="output">
      <Animation text1={outputText1} text2={outputText2} key={animationKey} />
    </div>
  {/if}
</div>

<style>
  .container {
    display: flex;
    justify-content: left;
    padding: 2rem;
    min-height: 500px;
    position: relative;
    overflow: visible;
    gap: 2rem;
  }

  .lines-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 1;
    overflow: visible;
  }

  .column {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
    z-index: 2;
  }

  .node {
    padding: 0.5rem 1rem;
    border-radius: 4px;
    cursor: pointer;
    transition: all 0.2s;
    position: relative;
    filter:blur(1px);

  }

  .node.selected {
    filter:blur(0px);
  }

  .output {
    position: fixed;
    bottom: 2rem;
    left: 50%;
    transform: translateX(-50%);
    padding: 1rem 2rem;
    background: white;
    opacity: 0.8;
    color: blue;
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    z-index: 2;
  }

  h3 {
  font-weight:600;
  filter: blur(1px);
  }
</style>