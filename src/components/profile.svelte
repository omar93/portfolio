<script>
  import { fade } from "svelte/transition"
  
let skills = [
  {name:'Javascript', duration: 7},
  {name:'HTML', duration: 10},
  {name:'CSS', duration: 10},
  {name:'Svelte', duration: 4},
  {name:'React', duration: 3},
]


</script>

<div id="wrapper" transition:fade={{delay: 500, duration: 1500 }} >

<div id="profile-wrapper" >
  <img src="https://lh3.googleusercontent.com/a/ACg8ocKC229kcaTuZxHPhFtt40sbChvyZVOeUQqKdVjQ-Nmu8A=s360-c-no" alt="Profile" >
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

</div>

</div>


<style>
  
#profile-wrapper {
  position: relative;
  display: flex;
  margin-left: 40px;
  overflow: hidden;
  width: 250px;
  height: 250px;
  box-shadow: 0 20px 35px rgba(0,0,0,0.3);
  border-radius: 10px;
  z-index: -2;
}

#profile-wrapper::before {
  content: "";
  background-color: white;
  width: 230%;
  height: 230%;
  position: absolute;
  left: -75%;
  top: -75%;
  animation: spin 3s linear infinite;
  background: conic-gradient(
    hsl(225 100% 50%),
    hsl(61, 100%, 50%),
    hsl(225 100% 50%),
    hsl(61, 100%, 50%)
  );
  z-index: -1;
}

#profile-wrapper::after {
  position: absolute;
  content: "";
  width: 98%;
  height: 98%;
  top: 1%;
  left: 1%;
  border-radius: 5px;
  background-color: white;
  overflow: hidden;
  z-index: -1;
}

@keyframes spin {
  to { transform: rotate(360deg) }
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
  width: 250px;
  padding: 15px;
  border-radius: 25px;
}

span {
  padding: 5px;
}

div > ul > span:first-child {
  font-size: 2rem;
}


</style>