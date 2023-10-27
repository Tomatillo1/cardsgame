<script>
    export let backgroundCards
</script>

<div class="cardsLocation">
    <img class="cardsBack" src="{backgroundCards}" alt="">
</div>

<style>
    .cardsLocation {
        background-color: black;
        width: 40% ;
        height: 80%;
    }

    .cardsBack {
        width: 100%;
    }

    @media screen and (max-width: 767px){
        .cardsLocation {
            display: flex;
            width: 75%;
            height: 35%;
        }
    }

    @media screen and (min-width: 768px) and (max-width: 1024px){
        .cardsLocation {
            display: flex;
            width: 60%;
            height: 40%;
        }
    }
</style>