<script>
  import { fade } from "svelte/transition"
  import Profile from "../components/profile.svelte"
  import Skills from "../components/skills.svelte"
  import BartBoard from "../lib/bartBoard.svelte";
</script>

<div id="wrapper">

  <div id="profile-sectin">
    <div id="profile-wrapper" transition:fade={{delay: 500, duration: 1500 }}>
      <Profile/>
    </div>
  
    <div id="skills-wrapper" transition:fade={{delay: 500, duration: 1500 }}>
      <Skills/>
    </div>
  </div>


  <div id="board-wrapper">
    <BartBoard/>
  </div>

</div>


<style>
  #wrapper {
    display: flex;
    justify-content: space-evenly;
    min-height: 100%;
  }

  #profile-wrapper {
    width: 290px;
    height: 250px;
    margin: 50px  0 0 50px;
  }

  #skills-wrapper {
    margin-left: 120px;
  }

  #board-wrapper {
    margin: 50px  0 0 50px;
  }
</style>