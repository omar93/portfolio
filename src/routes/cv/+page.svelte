<div id="brev">
  <div id="line1"></div>
  <div id="line2"></div>
</div>


<style>
  #brev {
    width: 100%;
    height: 100%;
    background-color: red;
    position: relative;
  }

  #line1 {
    position: absolute;
    border: 3px solid black;
    transform: rotate(25deg);
    transform-origin: top left;
    width: 55%;
    top: 0;
    left: 0;
  }

  #line2 {
    position: absolute;
    border: 3px solid black;
    transform: rotate(-25deg);
    transform-origin: top right;
    width: 55%;
    top: 0;
    right: 0;
  }
</style>