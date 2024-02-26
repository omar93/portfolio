<script>

  let text = 'Hej, jag heter omar & jobbar som frontend developer'
  let showingText = ''
  let letter = 0
  let intervalID

  const startWriting = _ => {
    intervalID = setInterval(() => {
      showingText += text.charAt(letter++)
      if(letter >= text.length) {
        letter = 0
      }
    }, 50);
  }

  startWriting()

  const stopWriting = _ => {
    clearInterval(intervalID)
  }
</script>

  <!-- svelte-ignore a11y-no-static-element-interactions -->
  <div on:mousedown={startWriting} on:mouseleave={stopWriting} on:mouseup={stopWriting}>
    <p>
      {showingText}
    </p>
  </div>

<style>
  div {
    border: 10px solid rgb(212, 126, 45);
    background-color: rgb(18, 92, 63);
    height: 300px;
    width: 450px;
    padding: 1rem;
  }
</style>