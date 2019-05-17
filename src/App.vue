<template>
  <div id="app">
    <div class="header">
      <div class="neon">retrosistema</div>
    </div>
    <div class="body">
      <div class="menu">
        <div class="option">
          <arcade-button></arcade-button>
          <span class="label">HOME</span>
        </div>
        <div class="option">
          <arcade-button></arcade-button>
          <span class="label">EVENTS</span>
        </div>
        <div class="option">
          <arcade-button></arcade-button>
          <span class="label">STORE</span>
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
body {
  background-color: #1e1e1e;
}
@font-face {
  font-family: "neon";
  src: url('./assets/fonts/chicago/ChicagoFlat.ttf');
}
@import url('https://fonts.googleapis.com/css?family=Press+Start+2P');
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: grid;
  grid-template-areas: 'header'
                        'body';

  .header {
    grid-area: header;
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
    grid-area: body;
    grid-gap: 10px;
    justify-items: center;
    .menu {
      display: grid;
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
