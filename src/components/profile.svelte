<script>
    import { fade } from "svelte/transition"
    
  let skills = [
    {name:'Javascript', duration: 7},
    {name:'HTML', duration: 10},
    {name:'CSS', duration: 10},
    {name:'Javascript', duration: 5},
  ]
</script>

<div id="wrapper" transition:fade={{delay: 500, duration: 1500 }}>

  <div id="profile-wrapper">
    <img src="https://lh3.googleusercontent.com/a/ACg8ocKC229kcaTuZxHPhFtt40sbChvyZVOeUQqKdVjQ-Nmu8A=s360-c-no" alt="Profile picture">
    <div id="contact-wrapper">
      <span>Omar</span>
      <span>Alhamad</span>
      <span>omar@codemaze.se</span>
      <span>+46765990141</span>
      <span>Stockholm</span>
    </div>
  </div>

  <div id="skills-wrapper">

    <ul>
    {#each skills as skill, i}
      {#if i === 0}
        <span>Skills:</span>
        <br><br>
      {/if }
      <div id="skill">
        <span>{skill.name}</span>
      </div>
    {/each}
    </ul>
  
    <ul>
    {#each skills as skill, i}
      {#if i === 0}
        <span>Exp:</span>
        <br><br>
      {/if }
      <div id="skill">
        <span>{skill.duration} Years</span>
      </div>
    {/each}
    </ul>
    
  </div>

</div>

<style>
  #wrapper {
    display: flex;
    flex-direction: column;
  }

  #profile-wrapper {
    display: flex;
  }

  #contact-wrapper {
    padding: 1rem;
    display: flex;
    flex-direction: column;
  }

  #skills-wrapper {
    display: flex;
    justify-content: space-between;
    width: 75%;
  }

  ul {
    padding: 1rem;
  }

  #skill {
    display: flex;
    justify-content: space-between;
    margin-top: 5px;
  }

  img {
    width: 35%;
    padding: 1rem;
  }

  span {
    padding: 5px;
  }

  div > ul > span:first-child {
    font-size: 2rem;
  }
</style>