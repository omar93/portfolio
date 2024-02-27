<script>
    import { fly, fade } from "svelte/transition"
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
    <footer transition:fade={{ delay: 0, duration: 750, y: 50 }}>
      <span transition:fly={{ delay: 0, duration: 750, y: 50 }}>Footer</span>
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
    min-height: 75px;
  }

  main {
    height: 100%;
  }


  footer {
    height: 50px;
    margin-top: auto;
    padding: .5rem;
    font-family: sans-serif;
    box-shadow: -0px 0px 10px 5px rgba(0, 0, 0, 0.05);
  }
</style>