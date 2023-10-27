<script>
    export let whatPlayer
    export let value
</script>

<label for="players">{whatPlayer}</label>
<input type="text" name="players" class="players" placeholder="Nom du joueur" maxlength="10" bind:value>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');

    .players {
        width: 30%;
        background: black;
        border: 1px solid white;
        color: white;
        font-size: 1rem;
        font-family: "Poppins", sans-serif;
        padding: 0.25rem 0.5rem 0.25rem 0.5rem;
    }

    .players::placeholder {
        color: white;
        opacity: 50%;
        font-style: italic;
        font-family: "Poppins", sans-serif;
    }

    label {
        color: white;
        font-family: "Poppins", sans-serif;
        font-size: 1.5rem;
    }

    @media screen and (max-width: 767px){
        .players {
            width: 50%;
        }
    }

    @media screen and (min-width: 768px) and (max-width: 1024px){
        .players {
            width: 50%;
            font-size: 2rem;
        }
        label {
            font-size: 3rem;
        }
    }
</style>
