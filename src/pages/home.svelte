<script>
    import InputName from "../lib/inputName.svelte";
    import {useNavigate} from "svelte-navigator";

    let newValue1 = ''
    let newValue2 = ''
    const navigate = useNavigate()

    function playGame() {

        if (newValue1 === '' && newValue2 === '') {
            alert("Aucun joueur n'a pas été défini")
        } else if (newValue1 === '' || newValue2 === '') {
            alert("Un des joueurs n'a pas été défini")
        } else {
            navigate(`/game?namePlayer1=${newValue1}&namePlayer2=${newValue2}`)

        }
    }
</script>

<h1>La bataille</h1>
<div class="inputMenu">
    <InputName whatPlayer={"Joueur numéro 1"} bind:value="{newValue1}"/>
    <InputName whatPlayer={"Joueur numéro 2"} bind:value="{newValue2}"/>
    <button on:click={playGame} class="playButton">Jouez</button>
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

    @media screen and (max-width: 767px){
        .playButton {
            width: 30%;
        }
    }

    @media screen and (min-width: 768px) and (max-width: 1024px){
        .playButton {
            width: 30%;
            font-size: 2rem;
        }
        h1 {
            font-size: 4rem;
        }
    }

</style>