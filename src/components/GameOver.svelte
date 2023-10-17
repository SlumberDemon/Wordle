<script>
    import {
        board,
        colors,
        createGrid,
        gameInfo,
        gameOver,
        GAME_WORD,
        guess,
        wordsList,
    } from "../store";
    import Board from "./Board.svelte";
    const retry = () => {
        const word = wordsList[Math.floor(Math.random() * wordsList.length)];
        GAME_WORD.set(word);
        console.log(word);

        gameInfo.set({
            attempt: 0,
            char: 0,
        });

        guess.set("");
        colors.set(createGrid());
        board.set(createGrid());
        gameOver.set(false);
    };
</script>

<div class="center">
    <h3>The correct word was: <strong>{$GAME_WORD}</strong></h3>
    <h3>Your guess: <strong>{$guess}</strong></h3>
</div>

<Board />

<div class="center">
    <button on:click={retry}>Retry</button>
</div>

<style>
    strong {
        font-weight: 900;
    }

    h3 {
        font-size: 2em;
    }

    button {
        background-color: var(--orange);
        color: white;
        border-radius: 4px;
        margin-top: 20px 50px;
        padding: 20px 50px;
        cursor: pointer;
        border: none;
        font-size: 24px;
    }

    .center {
        color: white;
        margin: 20px auto;
        width: fit-content;
        text-align: center;
    }
</style>
