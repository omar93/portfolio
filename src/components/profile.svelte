<script>
    import { fade } from "svelte/transition"
    import { onMount } from "svelte";
    
  let skills = [
    {name:'Javascript', duration: 7},
    {name:'HTML', duration: 10},
    {name:'CSS', duration: 10},
    {name:'Svelte', duration: 4},
    {name:'React', duration: 3},
  ]
  
  let gradient = 'gradient'


</script>

<div id="wrapper" transition:fade={{delay: 500, duration: 1500 }} >

  <div id="profile-wrapper">
    <img src="https://lh3.googleusercontent.com/a/ACg8ocKC229kcaTuZxHPhFtt40sbChvyZVOeUQqKdVjQ-Nmu8A=s360-c-no" alt="Profile" >
    <div id="contact-wrapper">
      <span>Omar</span>
      <span>Alhamad</span>
      <span>omar@codemaze.se</span>
      <span>0765990141</span>
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
  @property --rotate {
    syntax: "<angle>";
    initial-value: 132deg;
    inherits: false;
  }


  #wrapper {
    display: flex;
    flex-direction: column;
    padding: rem;
  }
  
  #profile-wrapper {
    background: rgb(255, 255, 255);
    padding: 1rem;
    position: relative;
    border-radius: 6px;
    display: flex;
    margin-left: 20px;
  }

  #profile-wrapper::before {
    content: "";
    position: absolute;
    width: 110%;
    height: 110%;
    top: -5%;
    left: -5%;
    border-radius: 6px;
    z-index: -1;
    background: linear-gradient(0.5turn, #3f87a6, #ebf8e1, #f69d3c);
    animation: spin 1s linear infinite;
    overflow: hidden;
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
    width: 135px;
    padding: 1rem;
    border-radius: 25px;
  }

  span {
    padding: 5px;
  }

  div > ul > span:first-child {
    font-size: 2rem;
  }


</style>