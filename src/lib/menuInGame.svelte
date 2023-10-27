<script>
    export let whatIsPerson
    export let whatIsScore
</script>

<div class="menuOrder">
    <p>{whatIsPerson}</p>
    <p>{whatIsScore}</p>
</div>



<style>
    .menuOrder {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }

    p {
        background: black;
        border: 1px solid white;
        color: white;
        font-size: 1rem;
        font-family: "Poppins", sans-serif;
        padding: 0.25rem 0.5rem 0.25rem 0.5rem;
        text-align: center;
        margin: 0;
    }

    @media screen and (max-width: 767px){
        .menuOrder {
            display: flex;
            flex-direction: row;
        }
    }

    @media screen and (min-width: 768px) and (max-width: 1024px){
        .menuOrder {
            display: flex;
            flex-direction: row;
        }
        p {
            font-size: 2rem;
        }
    }
</style>