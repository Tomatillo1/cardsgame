<script>
    import Menu from '../lib/menuInGame.svelte';
    import Cards from '../lib/cards.svelte';
    import PlayButton from '../lib/playButton.svelte';

    const params = new URLSearchParams(document.location.search);
    const name1 = params.get("namePlayer1");
    const name2 = params.get("namePlayer2");
    let imagelink;
    let imagelink2;
    let result = 0
    let result2 = 0

    function returnButton() {
        history.back()
    }

    function reverseCards(image, image2) {
        imagelink = image
        imagelink2 = image2

    }

    function scoring(cardsValue, cardsValue2) {
      let score;
        let score2;
        switch (cardsValue) {
            case "2" :
                score = 2;
                break;
            case "3" :
                score = 3;
                break;
            case "4" :
                score = 4;
                break;
            case "5" :
                score = 5;
                break;
            case "6" :
                score = 6;
                break;
            case "7" :
                score = 7;
                break;
            case "8" :
                score = 8;
                break;
            case "9" :
                score = 9;
                break;
            case "10" :
                score = 10;
                break;
            case "JACK" :
                score = 11;
                break;
            case "QUEEN" :
                score = 12;
                break;
            case "KING" :
                score = 13;
                break;
            case "ACE" :
                score = 14;
                break;
            default :
                score = 0;
        }

        switch (cardsValue2) {
            case "2" :
                score2 = 2;
                break;
            case "3" :
                score2 = 3;
                break;
            case "4" :
                score2 = 4;
                break;
            case "5" :
                score2 = 5;
                break;
            case "6" :
                score2 = 6;
                break;
            case "7" :
                score2 = 7;
                break;
            case "8" :
                score2 = 8;
                break;
            case "9" :
                score2 = 9;
                break;
            case "10" :
                score2 = 10;
                break;
            case "JACK" :
                score2 = 11;
                break;
            case "QUEEN" :
                score2 = 12;
                break;
            case "KING" :
                score2 = 13;
                break;
            case "ACE" :
                score2 = 14;
                break;
            default :
                score2 = 0;
        }

        if (score > score2) {
            result += 1
        } else if (score < score2) {
            result2 += 1
        }
    }

</script>

<button class="returnButton" on:click={returnButton}>retour</button>
<h1>La bataille</h1>
<div class="allPage">
    <div class="menuPlayers">
        <Menu whatIsPerson={name1} whatIsScore={result}/>
        <div class="cardsPacks">
            <Cards backgroundCards={"https://www.deckofcardsapi.com/static/img/back.png"}/>
            <Cards backgroundCards={imagelink}/>
        </div>
    </div>
    <div class="menuPlayers2">
        <Menu whatIsPerson={name2} whatIsScore={result2}/>
        <div class="cardsPacks2">
            <Cards backgroundCards={imagelink2}/>
            <Cards backgroundCards={"https://www.deckofcardsapi.com/static/img/back.png"}/>
        </div>
    </div>
</div>
<PlayButton {reverseCards} {scoring} {name1} {name2} {result} {result2}/>
<style>
    .allPage {
        display: flex;
        height: 75%;
    }

    .menuPlayers, .menuPlayers2 {
        display: flex;
        flex-direction: column;
        width: 50%;
        align-items: center;
        height: 100%;
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

    .cardsPacks, .cardsPacks2 {
        display: flex;
        flex-direction: row;
        width: 100%;
        height: 100%;
        justify-content: center;
        align-items: center;
        gap: 1rem;
    }

    @media screen and (max-width: 767px){
        .cardsPacks {
            display: flex;
            flex-direction: column;
        }
        .cardsPacks2 {
            display: flex;
            flex-direction: column-reverse;
        }
    }

    @media screen and (min-width: 768px) and (max-width: 1024px){
        .cardsPacks {
            display: flex;
            flex-direction: column;
        }
        .cardsPacks2 {
            display: flex;
            flex-direction: column-reverse;
        }
        h1 {
           font-size: 4rem;
        }
        .returnButton {
            font-size: 2rem;
            top: 1rem;
            left: 1rem;
        }
    }
</style>