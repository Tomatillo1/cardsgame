<script>
    import Menu from '../lib/menuInGame.svelte';
    import BackMenu from '../lib/EndGameButton.svelte';
    import Restart from '../lib/Restart.svelte';

    const params = new URLSearchParams(document.location.search);
    const name1 = params.get("namePlayer1");
    const name2 = params.get("namePlayer2");
    const score1 = params.get("scorePlayer1");
    const score2 = params.get("scorePlayer2");
</script>

<h1>La bataille</h1>
{#if score1 > score2}
    <h2><span class="color">{name1}</span> a gagné la partie</h2>
{:else if score1 < score2}
    <h2><span class="color">{name2}</span> a gagné la partie</h2>
{:else}
    <h2>Aucun joueur n'a gagné la partie</h2>
{/if}
<div class="dashBoard">
    <h3>Les scores :</h3>
    <div class="player">
        <Menu whatIsPerson={name1} whatIsScore={score1}/>
        <Menu whatIsPerson={name2} whatIsScore={score2}/>
    </div>
    <div class="button">
        <BackMenu/>
        <Restart/>
    </div>
</div>


<style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');

    h1 {
        color: white;
        text-align: center;
        margin-bottom: 0;
        font-family: "Poppins", sans-serif;
        outline: none;
    }

    h2 {
        color: white;
        font-size: 2.5rem;
        text-align: center;
        margin: 1rem 0 0 0;
        font-family: "Poppins", sans-serif;
        outline: none;
    }

    h3 {
        font-size: 2rem;
        color: white;
        margin: 0 0 1rem 0;
        text-align: center;
        font-family: "Poppins", sans-serif;
        outline: none;
    }

    .dashBoard {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100%;
        width: 100%;
        gap: 2rem;

    }

    .color {
        color: red;
    }

    .player {
        display: flex;
        flex-direction: row;
        justify-content: center;
        gap: 4rem;

    }

    .button {
        display: flex;
        flex-direction: row;
        gap: 2rem;
        width: 100%;
        justify-content: center;
    }

    @media screen and (max-width: 767px){
        .player {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }
        .button {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            align-items: center;
        }
    }

    @media screen and (min-width: 768px) and (max-width: 1024px){
        .player {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }
        .button {
            display: flex;
            gap: 4rem;
            align-items: center;
        }
        h1 {
            font-size: 4rem;
        }
        h2 {
            font-size: 3.5rem;
            padding: 0 1.5rem 0 1.5rem;
        }

        h3 {
            font-size: 3.5rem;
        }

        .dashBoard {
            gap: 3rem;
        }
    }
</style>