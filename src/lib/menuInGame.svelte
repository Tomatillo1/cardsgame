<script>
    export let whatIsPerson
</script>

<div class="menuOrder">
    <p>{whatIsPerson}</p>
    <p>0</p>
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
</style>