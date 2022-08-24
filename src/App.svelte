<script type="text/typescript">
  import {Alignment, Fit, Layout, Rive} from '@rive-app/canvas';

  import {onMount} from 'svelte'
  let canvas:any
  let logo = "assets/images/favicon.ico"
  let tree = "assets/images/car.riv"

  onMount( async ()=>{
    const r = new Rive({
        src: tree,
        canvas: canvas,
        autoplay:true,
        animations:"idleLoop"
    })
    r.layout = new Layout({fit:Fit.Cover,alignment:Alignment.Center})
    
  })
</script>

<main>
  <canvas class="bg" bind:this={canvas}/>
  <br/>
  <img class="logo" src={logo} alt="logo"/>
  <a href="http://rsui.cexup.com" target="_blank">Go to rsui App</a>
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  canvas {
    width: 100%;
  }

  .logo {
    position: absolute;
    top: 0;
    bottom: 0;
  }

  canvas {
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

  img {
    height: 50px;
    width: 50px;
  }


  @media (min-width: 480px) {
    h1 {
      max-width: none;
    }

    p {
      max-width: none;
    }
  }
</style>
