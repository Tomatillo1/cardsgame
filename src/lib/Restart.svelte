<script>
    import {useNavigate} from "svelte-navigator";
    const navigate = useNavigate()

    function restartGame() {
        history.back()
    }
</script>

<button class="restartButton" on:click={restartGame}>Rejouer</button>

<style>
    .restartButton {
        background: black;
        border: 1px solid white;
        color: white;
        font-size: 1.5rem;
        font-family: "Poppins", sans-serif;
        padding: 0.25rem 0.5rem 0.25rem 0.5rem;
        margin-top: 1rem;
    }

    @media screen and (max-width: 767px){
        .restartButton {
            width: 35%;
        }
    }

    @media screen and (min-width: 768px) and (max-width: 1024px){
        .restartButton {
            width: 30%;
            font-size: 2.5rem;
        }
    }
</style>