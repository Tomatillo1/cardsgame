<script>
    import {Router, Route, Link, useNavigate} from "svelte-navigator";
    import Home from "./pages/home.svelte";
    import Game from './pages/game.svelte';
    import Popup from './pages/PopupEndgame.svelte';
</script>
<Router>
    <Route path="/">
        <Home/>
    </Route>
    <Route path="game">
        <Game/>
    </Route>
    <Route path="popup">
        <Popup/>
    </Route>
</Router>