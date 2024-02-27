<script>

  let text = `Jag är en effektiv individ med stark
självmotivation och positiv envishet. Bevis
på min självmotiverande natur och
uthållighet är min framgångsrika
viktnedgång på 50 kg på bara 6 månader.
Jag är en naturlig problemlösare med
ständigt fokus på personlig utveckling.
Mitt intresse för datorer och ny teknologi
reflekteras i min passion för kodning och
skapandet av innovativa lösningar,
exempelvis inom hemautomation och
apputveckling för optimerade matinköp`

  let showingText = ''
  let letter = 0
  let intervalID

  const startWriting = _ => {
    intervalID = setInterval(() => {
      showingText += text.charAt(letter++)
      if(letter >= text.length) {
        stopWriting()
        letter = 0
      }
    }, 25);
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
    border-radius: 1rem;
    color: white;
    height: 300px;
    width: 450px;
    padding: 1rem;
    /* border-image: url('/tra.avif') 50 / 15px / 5px round; */
    word-break: break-word;
  }
</style>