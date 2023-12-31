<script lang="ts">
  import { Router, Route, Link } from 'svelte-routing';
  import Home from './pages/Home.svelte';
  import About from './pages/About.svelte';

  let version: string = '1.0.0';
</script>

<Router>
  <nav class="menu">
    <Link to="/">Home</Link>
    <Link to="/about">About</Link>
  </nav>

  <Route path="/" component={Home} />
  <Route path="/about" component={About} />
</Router>

<footer>
  <p>Version: {version}</p>
</footer>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(145deg, #0d0d0d, #262626);
    color: #ccc;
    height: 100vh;
    width: 100vw;
    display: flex;
    flex-direction: column;
    align-items: center;
    overflow: auto;
  }

  .menu {
    width: 100%;
    background: #111;
    padding: 1em 0;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
    text-align: center;
  }

  :global(a.active) {
    color: #fefefe;
    text-shadow: 0 0 10px rgba(255, 255, 255, 0.85);
  }

  footer {
    padding: 1rem;
    text-align: center;
    width: 100%;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
  }

  footer p {
    font-size: 0.9rem;
    color: #999;
  }
</style>

