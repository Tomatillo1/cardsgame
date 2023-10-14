<script>
    import InputName from './lib/inputName.svelte';

    let newValue1 = ''
    let newValue2 = ''
    let goToTheGame = true

    function playGame() {
        if (newValue1 === '' && newValue2 === '') {
            alert("Aucun joueur n'a pas été défini")
        } else if (newValue1 === '' || newValue2 === '') {
            alert("Un des joueurs n'a pas été défini")
        } else {
            console.log({newValue1}, {newValue2})
            goToTheGame = false
        }
    }
</script>

{#if goToTheGame === true}
    <h1>La bataille</h1>
    <div class="inputMenu">
        <InputName whatPlayer={"Joueur numéro 1"} bind:value="{newValue1}"/>
        <InputName whatPlayer={"Joueur numéro 2"} bind:value="{newValue2}"/>
        <button on:click={playGame} class="playButton">Jouez</button>
    </div>
{:else}
    <p>uwu</p>
{/if}

<style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');

    h1 {
        color: white;
        text-align: center;
        margin-bottom: 0;
        font-family: "Poppins", sans-serif;
    }

    .inputMenu {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100%;
        gap: 1.5rem;
    }

    .playButton {
        width: 15%;
        background: black;
        border: 1px solid white;
        color: white;
        font-size: 1rem;
        font-family: "Poppins", sans-serif;
        padding: 0.25rem 0.5rem 0.25rem 0.5rem;
        margin-top: 1rem;
    }

    p {
        color: white;
    }
</style>