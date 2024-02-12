<script>
  import '$lib/reset.css'
  import Menu from '../components/menu.svelte'

  let visable = false
  setTimeout(() => visable = true, 0)

</script>

{#if visable}
  <div id="page--wrapper">
    <header>
      <Menu/>
    </header>
    <main>
      <slot></slot>
    </main>
    <footer>
      <span>Footer</span>
    </footer>
  </div>
{/if}

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
    font-family: sans-serif;
  }
</style>