<script>
  import '$lib/reset.css'
  import Menu from '../components/menu.svelte';
</script>

<div id="page--wrapper">
  <header>
    <Menu/>
  </header>
  <main>
    <slot></slot>
  </main>
  <footer>Footer</footer>
</div>

<style>
  #page--wrapper {
    height: 100vh;
    width: 100vw;
    display: flex;
    flex-direction: column;
  }

  header {
    min-height: 50px;
    padding: .5rem;
  }

  main {
    height: 100%;
  }


  footer {
    height: 50px;
    margin-top: auto;
    padding: .5rem;
  }
</style>