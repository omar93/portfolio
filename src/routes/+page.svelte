<script>
  import { fly } from "svelte/transition"
  import Profile from "../components/profile.svelte"
</script>

<div id="wrapper" transition:fly={{ delay: 300, duration: 1000, x: -500 }}>
  <Profile/>
</div>

<style>
  #wrapper {
    width: 25%;
    min-height: 100%;
  }
</style>