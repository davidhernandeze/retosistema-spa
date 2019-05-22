<template>
  <div id="app">
    <div class="background">
      <div class="image"></div>
    </div>
    <div class="header">
      <div class="neon">retrosistema</div>
    </div>
    <div class="body">
      <div class="menu">
        <div class="option">
          <arcade-button></arcade-button>
          <span class="label">INICIO</span>
        </div>
        <div class="option">
          <arcade-button></arcade-button>
          <span class="label">EVENTOS</span>
        </div>
        <div class="option">
          <arcade-button></arcade-button>
          <span class="label">TIENDA</span>
        </div>
      </div>
      <screen></screen>
    </div>
  </div>
</template>
<script>
import Screen from './components/Screen'
import ArcadeButton from './components/ArcadeButton'
export default {
  components: { ArcadeButton, Screen }
}
</script>
<style lang="scss">
html, body {
  background-color: #272a35;
  margin: 0;
  height: 100%;
}
.background {
  @keyframes zoom {
    from {
      transform: scale(1);
    }

    to {
      transform: scale(1.1);
      filter: brightness(150%);
    }
  }

  .image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: red url('http://unsplash.it/1500/1500?random');
    background-size: cover;
    transform: scale(1.1);
    background-blend-mode: hard-light;

    &::before,
    &::after {
      position: absolute;
      top: 0;
      left: 0px;
      width: 100%;
      height: 100%;
      background: blue url('http://unsplash.it/1500/1500?random');
      background-size: cover;
      content: '';
      mix-blend-mode: difference;
      background-blend-mode: hard-light;
    }

    &::before {
      animation-name: zoom;
      animation-duration: 1s;
      animation-iteration-count: infinite;
      animation-direction: alternate;
    }

    &::after {
      animation-name: zoom;
      animation-duration: 1s;
      animation-iteration-count: infinite;
      animation-direction: alternate;
      background-blend-mode: hard-light;
      animation-delay: .5s;
    }
  }
}
@font-face {
  font-family: "neon";
  src: url('./assets/fonts/chicago/ChicagoFlat.ttf');
}
@import url('https://fonts.googleapis.com/css?family=Press+Start+2P');
#app {
  height: 100%;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: grid;
  grid-template-rows: 100px auto;
  grid-gap: 20px;

  .header {
    .neon {
      font-family: neon;
      color: #41b883;
      font-size: 400%;
      line-height: 9rem;
      text-shadow: 0 0 3vw '#F40A35';
    }
    .neon {
      animation: neon 5s ease infinite;
    }

    @keyframes neon {
      0%,
      100% {
        text-shadow: 0 0 1vw #782133, 0 0 3vw #782133, 0 0 5vw #782133, 0 0 5vw #782133, 0 0 .4vw #782133, .5vw .5vw .1vw #806914;
        color: #9ca268;
      }
      50% {
        text-shadow: 0 0 1vw #FA1C16, 0 0 3vw #FA1C16, 0 0 5vw #FA1C16, 0 0 5vw #FA1C16, 0 0 .4vw #FED128, .5vw .5vw .1vw #806914;
        color: #FED128;
      }
    }
  }
  .body {
    display: grid;
    justify-items: center;
    .menu {
      display: grid;
      align-items: center;
      grid-template-columns: auto auto auto;
      column-gap: 50px;

      .label {
        font-size: 0.7em;
        font-family: 'Press Start 2P', cursive;
        color: white;
      }
    }
  }
}
</style>
