<script>
    
    import {Router, Link, Route} from "svelte-routing"
    import Login from "./page/Login.svelte"
    import Home from "./page/Home.svelte"
    import Editor from "./page/Editor.svelte"

    let url = '/';
</script>

<Router url={url}>
    <div>
        <Route path='/'>
            <Login/>
        </Route>
        <Route path='home'>
            <Home/>
        </Route>
        <Route path='editor'>
            <Editor/>
        </Route>
    </div>
</Router>

