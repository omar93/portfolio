<script>
  import { fly } from "svelte/transition"
  import Profile from "../components/profile.svelte"
</script>

<div id="wrapper" transition:fly={{ delay: 300, duration: 1000, x: -500 }}>
  <div id="profile-wrapper">
    <Profile/>
  </div>
</div>

<style>
  #wrapper {
    display: grid;
    min-height: 100%;
  }

  #profile-wrapper {
    width: 30%;
  }
</style>