<script>
  import { fly, fade } from "svelte/transition"
  let links = [ 
    {name:'Github', url:'http://www.Github.com/omar93'},
    {name:'Linkedin', url:'https://www.linkedin.com/in/omar-alhamad-435a25a6/'}
  ]
</script>

<div id="wrapper" transition:fade={{ delay: 0, duration: 750, y: -50 }}>
  <ul transition:fly={{ delay: 0, duration: 750, y: -50 }}>
    {#each links as link}
      <a target="_blank" href="{link.url}">{link.name}</a>
    {/each}
  </ul>
</div>

<style>
  #wrapper {
    margin-top: -10px;
    width: 100%;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    height: 100%;
  }
  ul {
    height: 100%;
    box-shadow: -0px 0px 10px 5px rgba(0, 0, 0, 0.05);
    border-radius: 5px;
    align-items: center;
    display: flex;
    width: 100%;
    justify-content: space-evenly;
    font-size: 1.5rem;
  }

  a {
    text-decoration: none;
    font-family: sans-serif;
  }
</style>