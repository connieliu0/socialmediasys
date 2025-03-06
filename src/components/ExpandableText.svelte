<script>
    export let mainText = "";
    export let addendumText = "";
    let isExpanded = false;

    function handleClickOutside(event) {
        const container = event.target.closest('.expandable-container');
        if (!container && isExpanded) {
            isExpanded = false;
        }
    }

    function toggleExpand(event) {
        event.stopPropagation();
        isExpanded = !isExpanded;
    }

    // Add and remove click listener
    import { onMount, onDestroy } from 'svelte';

    onMount(() => {
        document.addEventListener('click', handleClickOutside);
    });

    onDestroy(() => {
        document.removeEventListener('click', handleClickOutside);
    });
</script>

<div class="expandable-container">
    <span class="main-text" on:click={toggleExpand}>{mainText}</span>
    <div class="addendum" class:show={isExpanded} on:click|stopPropagation>
        {addendumText}
    </div>
</div>

<style>
    .expandable-container {
        position: relative;
        display: inline;
    }

    .main-text {
        cursor: pointer;
        text-decoration: underline;
        text-decoration-style: dotted;
        text-underline-offset: 4px;
        color: inherit;
    }

    .addendum {
        position: absolute;
        left: 50%;
        bottom: 100%;
        transform: translateX(-50%) translateY(10px);
        background-color: #0035ff;
        color: white;
        padding: 1rem;
        border-radius: 0.5rem;
        margin-bottom: 0.5rem;
        font-size: 0.9em;
        width: 200px;
        opacity: 0;
        pointer-events: none;
        transition: all 0.3s ease;
        z-index: 9999;
        text-align: left;
        filter: blur(0.2px);
        box-shadow: 0 0 10px rgba(0, 53, 255, 0.2);
    }

    .addendum.show {
        opacity: 1;
        transform: translateX(-50%) translateY(0);
        pointer-events: auto;
    }

    @media (max-width: 768px) {
        .expandable-container {
            display: inline-block;
        }

        .addendum {
            position: relative;
            left: 0;
            bottom: auto;
            transform: none;
            margin-top: 0.5rem;
            width: 100%;
            max-width: 200px;
            display: none;
        }

        .addendum.show {
            display: block;
            transform: none;
        }
    }
</style> 