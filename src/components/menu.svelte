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
    width: 100%;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    height: 100%;
  }
  ul {
    display: flex;
    width: 40%;
    justify-content: space-evenly;
  }

  a {
    text-decoration: none;
    font-family: sans-serif;
  }
</style>