<script>
    import {Router, Route, Link, useNavigate} from "svelte-navigator";
    import Home from "./pages/home.svelte"
    import Game from './pages/game.svelte';
</script>
<Router>
    <Route path="/">
        <Home/>
    </Route>
    <Route path="game">
        <Game/>
    </Route>
</Router>