<script>
  import { gameOver } from "./store";
  import { fade } from "svelte/transition";
  import Board from "./components/Board.svelte";
  import Keyboard from "./components/Keyboard.svelte";
  import GameOver from "./components/GameOver.svelte";
</script>

<main>
  <nav>Space Wordle</nav>

  {#if $gameOver}
    <div in:fade={{ duration: 1000 }}>
      <GameOver />
    </div>
  {:else}
    <div in:fade={{ duration: 800 }}>
      <Board />
      <Keyboard />
    </div>
  {/if}
</main>

<style>
  nav {
    color: white;
    font-weight: bold;
    padding: 15px;
    font-size: 2em;
    text-align: center;
  }
</style>
