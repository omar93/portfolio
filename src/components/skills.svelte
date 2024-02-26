<script>
import { fade, fly } from "svelte/transition"
  
let skills = [
  {name:'Javascript', duration: 7},
  {name:'HTML', duration: 10},
  {name:'CSS', duration: 10},
  {name:'Svelte', duration: 4},
  {name:'React', duration: 3},
]

let skillVisable = false
let delay = 300

setTimeout(() => {
  skillVisable = true
}, delay);

const increaseDelay = _ => {
  delay += 250
  return delay
}
</script>

<div id="skills-wrapper">
  <ul>
  {#each skills as skill, i}

    {#if skillVisable}

      {#if i === 0}
        <span>Skills:</span>
        <br><br>
      {/if}
        <div id="skill" transition:fly={{ delay: increaseDelay(), duration: 1000, x: -500 }}>
          <span>{skill.name}</span>
        </div>
      {/if}

  {/each}
  </ul>
</div>



<style>
 
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


span {
  padding: 5px;
}

div > ul > span:first-child {
  font-size: 2rem;
}


</style>