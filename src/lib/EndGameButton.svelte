<script>
    import {useNavigate} from "svelte-navigator";
    const navigate = useNavigate()

    function returnMenu() {
        navigate('/')
    }
</script>

<button class="returnButton" on:click={returnMenu}>Menu</button>

<style>
    .returnButton {
        background: black;
        border: 1px solid white;
        color: white;
        font-size: 1.5rem;
        font-family: "Poppins", sans-serif;
        padding: 0.25rem 0.5rem 0.25rem 0.5rem;
        margin-top: 1rem;
    }
    @media screen and (max-width: 767px){
        .returnButton {
            width: 35%;
        }
    }

    @media screen and (min-width: 768px) and (max-width: 1024px){
        .returnButton {
            width: 30%;
            font-size: 2.5rem;
        }
    }
</style>