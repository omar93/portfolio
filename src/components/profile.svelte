<script>
  import { fly } from "svelte/transition"
  
</script>

<div id="profile-wrapper" transition:fly={{ delay: 300, duration: 1000, x: -500 }}>
  <img src="https://lh3.googleusercontent.com/a/ACg8ocKC229kcaTuZxHPhFtt40sbChvyZVOeUQqKdVjQ-Nmu8A=s360-c-no" alt="Profile" >
</div>

<style>
  
#profile-wrapper {
  position: relative;
  display: flex;
  overflow: hidden;
  width: 250px;
  height: 250px;
  box-shadow: 0 20px 35px rgba(0,0,0,0.3);
  border-radius: 50%;
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
  animation: spin 3.14s linear infinite;
  background: conic-gradient(from 90deg at 50% 50%, rgba(241, 255, 0, 1) 25%, rgba(0, 203, 230, 1) 50%);
  z-index: -1;
}

#profile-wrapper::after {
  position: absolute;
  content: "";
  width: 98%;
  height: 98%;
  top: 1%;
  left: 1%;
  border-radius: 50%;
  background-color: white;
  overflow: hidden;
  z-index: -1;
}

@keyframes spin {
  to { transform: rotate(360deg) }
}




img {
  width: 250px;
  padding: 10px;
  border-radius: 50%;
}


</style>