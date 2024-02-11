<script>
  let links = [
    'Home',
    'CV',
    'Github',
    'Linkedin'
  ]
</script>

<div id="wrapper">
  <ul>
    {#each links as link}
      <a href="/{link}">{link}</a>
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