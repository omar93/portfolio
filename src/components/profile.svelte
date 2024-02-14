<script>
    import { fade } from "svelte/transition"
    
  let skills = [
    'JavaScript / Typescript',
    'NodeJS',
    'React',
    'Svelte / Kit',
    'Express',
    'Java',
    'SQL / NoSQL',
    'Git',
    'Docker / Kubernetes'

  ]
  
  let clicked = false
  const test = () => {
  }


</script>

<div id="wrapper" transition:fade={{delay: 500, duration: 1500 }} >

  <div id="profile-wrapper" class={clicked ? "spon" : "spin"}>
    <div id="top-left-to-bottom-right"></div>
    <div id="top-right-to-bottom-left"></div>  
    <img src="https://lh3.googleusercontent.com/a/ACg8ocKC229kcaTuZxHPhFtt40sbChvyZVOeUQqKdVjQ-Nmu8A=s360-c-no" alt="Profile" >
  </div>

  <div id="contact-wrapper" anchor="profile-wrapper">
    <p>Fullstack utvecklare, som leverar kvalité,
      HTML, CSS & Javascript expert</p>
  </div>

</div>


<style>
  #wrapper {
    position: relative;
  }

  #profile-wrapper {
    position: relative;
    display: flex;
    margin-left: 20px;
    overflow: hidden;
    width: 1000px;
    height: 500px;
    box-shadow: 0 20px 35px rgba(0,0,0,0.3);
    border-radius: 10px;
    z-index: -2;
    
  }

  #profile-wrapper::before {
    content: "";
    background-color: white;
    width: 250%;
    height: 250%;
    position: absolute;
    left: -75%;
    top: -75%;
    animation: spin 4s linear infinite;
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

  
  #contact-wrapper {
    padding: 1rem;
    top: -200px;
    left: 200px;
    position: relative;
    text-wrap: wrap;
    word-break: break-word;
  }

  #top-left-to-bottom-right {
    position: absolute;
    border: 5px solid black;
    border-radius: 50px;
    transform: rotate(25deg);
    transform-origin: top left;
    width: 53.5%;
    top: 3px;
    left: 10px;
  }

  #top-right-to-bottom-left {
    position: absolute;
    border: 5px solid black;
    border-radius: 50px;
    transform: rotate(-25deg);
    transform-origin: top right;
    width: 53.5%;
    top: 3px;
    right: 12px;
  }

  p {
    width: 200px;
  }

  img {
    width: 200px;
    height: 200px;
    padding: 15px;
    border-radius: 25px;
    z-index: 3;
  }



</style>