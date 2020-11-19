<script>
  import { fade } from "svelte/transition";
  export let name;

  let isReady = false;
</script>

<!-- Fade - opacity 0 - 1
Blur - opacity and blur
Fly - x and y along with opacity
Slide - height
Scale - start: scale, opacity
Draw - draw svgs -->
<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  {#if isReady}
    <h1 transition:fade>Hello {name}!</h1>
  {/if}
  <button on:click={() => (isReady = !isReady)}>Fade in</button>
  <p>
    Visit the
    <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
    to learn how to build Svelte apps.
  </p>
</main>
