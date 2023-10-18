<script>
    import Menu from '../lib/menuInGame.svelte';
    import Cards from '../lib/cards.svelte';
    import PlayButton from '../lib/playButton.svelte';

    const params = new URLSearchParams(document.location.search);
    let name1 = params.get("namePlayer1");
    let name2 = params.get("namePlayer2");

    function returnButton() {
        history.back()
    }
</script>

<button class="returnButton" on:click={returnButton}>retour</button>
<h1>La bataille</h1>
<div class="allPage">
    <div class="menuPlayers">
        <Menu whatIsPerson={name1}/>
        <div class="cardsPacks">
            <Cards/>
            <Cards/>
        </div>
    </div>
    <div class="menuPlayers">
        <Menu whatIsPerson={name2}/>
        <div class="cardsPacks">
            <Cards/>
            <Cards/>
        </div>
    </div>
</div>
<PlayButton/>
    <style>
        .allPage {
            display: flex;
            height: 75%;
        }

        .menuPlayers {
            display: flex;
            flex-direction: column;
            width: 50%;
            align-items: center;
            height: 100%;
            gap: 2rem;
        }

        h1 {
            color: white;
            text-align: center;
            font-family: "Poppins", sans-serif;
            outline: none;
        }

        .returnButton {
            background: black;
            border: 1px solid white;
            color: white;
            font-size: 1rem;
            font-family: "Poppins", sans-serif;
            padding: 0.25rem 0.5rem 0.25rem 0.5rem;
            position: absolute;
            top: 0.5rem;
            left: 0.5rem;
        }

        .cardsPacks {
            display: flex;
            flex-direction: row;
            width: 100%;
            height: 100%;
            justify-content: center;
            align-items: center;
            gap: 1rem;
        }
    </style>