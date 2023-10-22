<script>
    import { onMount } from 'svelte';
    let deck1;
    let deck2;

    onMount(() => {
        deckCreation()
    });
    function deckCreation () {
        fetch('https://www.deckofcardsapi.com/api/deck/new/shuffle/?deck_count=2')
            .then(response => {
                console.log(response)
                return response.json();
            })
            .then(users => {
                deck1 = users.deck_id
                console.log(deck1)
            });
        fetch('https://www.deckofcardsapi.com/api/deck/new/shuffle/?deck_count=2')
            .then(response => {
                return response.json();
            })
            .then(users => {
                deck2 = users.deck_id
                console.log(deck2)
            });
    }

    function takeCards () {
        fetch(`'https://deckofcardsapi.com/api/deck/${deck1}/draw/?count=1'`)
            .then(response => {
                console.log(response)
                return response.json();
            })
            .then(users => {
                console.log(users)
            });
        fetch(`'https://deckofcardsapi.com/api/deck/${deck2}/draw/?count=1'`)
            .then(response => {
                return response.json();
            })
            .then(users => {
                console.log(users)
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