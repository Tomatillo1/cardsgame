<script>
    import {useNavigate} from "svelte-navigator";
    import {onMount} from 'svelte';
    const navigate = useNavigate()
    let deck1;
    export let name1;
    export let name2;
    export let reverseCards;
    export let scoring;

    onMount(() => {
        deckCreation()
    });

    function deckCreation() {
        fetch('https://www.deckofcardsapi.com/api/deck/new/shuffle/?deck_count=1')
            .then(response => {
                return response.json();
            })
            .then(users => {
                deck1 = users.deck_id
            });
    }

    function takeCards() {
        let image;
        let image2;
        let cardsValue;
        let cardsValue2;
        fetch(`https://deckofcardsapi.com/api/deck/${deck1}/draw/?count=2`)
            .then(response => {
                return response.json();
            })
            .then(users => {
                image = users.cards[0].image
                image2 = users.cards[1].image
                cardsValue = users.cards[0].value
                cardsValue2 = users.cards[1].value
                reverseCards(image, image2)
                scoring(cardsValue, cardsValue2)
                if (users.remaining === 0) {
                    navigate(`/popup?namePlayer1=${name1}&namePlayer2=${name2}`)
                }
            });
    }
</script>

<button class="play" on:click={takeCards}>Retourner les cartes</button>

<style>
    .play {
        background: black;
        border: 1px solid white;
        color: white;
        font-size: 1rem;
        font-family: "Poppins", sans-serif;
        padding: 0.25rem 0.5rem 0.25rem 0.5rem;
        width: 20%;
        align-self: center;
    }
</style>