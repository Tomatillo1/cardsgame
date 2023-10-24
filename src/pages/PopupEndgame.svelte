<script>
    const params = new URLSearchParams(document.location.search);
    const name1 = params.get("namePlayer1");
    const name2 = params.get("namePlayer2");
</script>

<h1>La bataille</h1>
<div class="dashBoard">
    <div class="card">
        <img src="https://www.deckofcardsapi.com/static/img/back.png" alt="">
    </div>
    <div class="menu">

    </div>
</div>


<style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');

    h1 {
        color: white;
        text-align: center;
        margin-bottom: 0;
        font-family: "Poppins", sans-serif;
        outline: none;
    }
    
    .dashBoard {
        display: flex;
        flex-direction: row;
        height: 100%;
    }

    .card {
        display: flex;
        flex-direction: column;
        width: 30%;
        height: 100%;
        justify-content: center;
        align-items: center;
    }

    .menu {
        width: 70%;
    }
</style>