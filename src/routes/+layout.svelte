<script>
  import { fly } from "svelte/transition"
  import '$lib/reset.css'
  import Menu from '../components/menu.svelte'
  import Footer from "../components/footer.svelte";

  let visable = false
  setTimeout(() => visable = true, 0)

  let duration = 10000
  
  const getDuration = async () => {
    
    setTimeout(() => {
      duration = 2000
      
    }, 2500);

    // clearTimeout(timeout)
    return duration
  }

  getDuration()

</script>

{#if visable}
  <div id="page--wrapper">
    <header>
      <Menu/>
    </header>
    <main>
      <slot></slot>
    </main>
    <footer transition:fly={{ delay: 250, duration: getDuration(), y: -500 }}>
      <Footer/>
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