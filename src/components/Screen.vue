<template>
  <div class="screen">
    <div class="main">
      <div class="info">
        <span>1 Baila conmigo</span>
        <span>2 Lo escencial</span>
        <span>3 Mary</span>
        <span>4 Vere caer el sol</span>
        <span>5 En lo profundo</span>
        <span>6 Escudo de piedra</span>
      </div>
      <img class="tsuru" src="../assets/img/tsuru.gif" alt="">
      <div class="lines"></div>
      <div class="noise"></div>
      <div class="message" data-splitting>BIENVENIDO</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Screen',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.screen {
  .main {
    position: relative;
    font-family: 'Press Start 2P', cursive;
    color: #fff;
    width: 70vw;
    height: 60vmax;
    max-height: 60vh;
    background: #193095;
    z-index: 1000;
    min-width: 300px;

    @media screen and (max-width: 320px) {
      width: 100%;
    }

    .info {
      padding: 1%;
      right: 5%;
      top: 20%;
      position: absolute;
      background: #152771;
      width: 40%;
      height: 60%;
      display: grid;
      font-size: 0.8em;
      align-items: center;
      justify-items: center;
    }
  }
  .tsuru {
    position:absolute;
    width: 40%;
    left: 5%;
    top: 40%;
  }

  .noise {
    overflow: hidden;
    pointer-events: none;
    opacity: 1;
  }

  .noise:before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: url('https://ice-creme.de/images/background-noise.png');
    pointer-events: none;
    will-change: background-position;
    animation: noise 1s infinite alternate;
  }

  .lines {
    position: relative;
    width: 100%;
    height: 100%;
    pointer-events: none;
    opacity: 0.6;
    will-change: opacity;
    animation: opacity 3s linear infinite;

    &:before {
      content: '';
      position: absolute;
      left: 0;
      top: 0;
      right: 0;
      bottom: 0;
      pointer-events: none;
      background: linear-gradient(to bottom, transparent 50%, rgba(0, 0, 0, .5) 51%);
      background-size: 100% 4px;
      will-change: background, background-size;
      animation: scanlines 0.2s linear infinite;
    }
  }

  .main .noise:before {
    background-size: 150%;
  }

  .main .message {
    letter-spacing: 5px;
    position: absolute;
    left: 2rem;
    top: 2rem;
    will-change: text-shadow;
    animation: rgbText 2s steps(9) 0s infinite alternate;
  }

  .main .message .char {
    will-change: opacity;
    animation: type 1.2s infinite alternate;
    animation-delay: calc(60ms * var(--char-index));
  }

  .main .time {
    position: absolute;
    right: 2rem;
    top: 2rem;
    will-change: text-shadow;
    animation: rgbText 1s steps(9) 0s infinite alternate;
  }

  .main .counter {
    position: absolute;
    left: 2rem;
    bottom: 2rem;
    will-change: text-shadow;
    animation: rgbText 1s steps(9) 0s infinite alternate;
  }

  @keyframes noise {
    0%,
    100% {
      background-position: 0 0;
    }
    10% {
      background-position: -5% -10%;
    }
    20% {
      background-position: -15% 5%;
    }
    30% {
      background-position: 7% -25%;
    }
    40% {
      background-position: 20% 25%;
    }
    50% {
      background-position: -25% 10%;
    }
    60% {
      background-position: 15% 5%;
    }
    70% {
      background-position: 0 15%;
    }
    80% {
      background-position: 25% 35%;
    }
    90% {
      background-position: -10% 10%;
    }
  }

  @keyframes opacity {
    0% {
      opacity: 0.6;
    }
    20% {
      opacity: 0.3;
    }
    35% {
      opacity: 0.5;
    }
    50% {
      opacity: 0.8;
    }
    60% {
      opacity: 0.4;
    }
    80% {
      opacity: 0.7;
    }
    100% {
      opacity: 0.6;
    }
  }

  @keyframes scanlines {
    from {
      background: linear-gradient(to bottom, transparent 50%, rgba(0, 0, 0, .5) 51%);
      background-size: 100% 4px;
    }
    to {
      background: linear-gradient(to bottom, rgba(0, 0, 0, .5) 50%, transparent 51%);
      background-size: 100% 4px;
    }
  }

  @keyframes rgbText {
    0% {
      text-shadow: -1px 1px 8px rgba(255, 255, 255, 0.6), 1px -1px 8px rgba(255, 255, 235, 0.7), 0px 0 1px rgba(251, 0, 231, 0.8), 0 0px 3px rgba(0, 233, 235, 0.8), 0px 0 3px rgba(0, 242, 14, 0.8), 0 0px 3px rgba(244, 45, 0, 0.8), 0px 0 3px rgba(59, 0, 226, 0.8);
    }
    25% {
      text-shadow: -1px 1px 8px rgba(255, 255, 255, 0.6), 1px -1px 8px rgba(255, 255, 235, 0.7), 0px 0 1px rgba(251, 0, 231, 0.8), 0 0px 3px rgba(0, 233, 235, 0.8), 0px 0 3px rgba(0, 242, 14, 0.8), 0 0px 3px rgba(244, 45, 0, 0.8), 0px 0 3px rgba(59, 0, 226, 0.8);
    }
    45% {
      text-shadow: -1px 1px 8px rgba(255, 255, 255, 0.6), 1px -1px 8px rgba(255, 255, 235, 0.7), 5px 0 1px rgba(251, 0, 231, 0.8), 0 5px 1px rgba(0, 233, 235, 0.8), -5px 0 1px rgba(0, 242, 14, 0.8), 0 -5px 1px rgba(244, 45, 0, 0.8), 5px 0 1px rgba(59, 0, 226, 0.8);
    }
    50% {
      text-shadow: -1px 1px 8px rgba(255, 255, 255, 0.6), 1px -1px 8px rgba(255, 255, 235, 0.7), -5px 0 1px rgba(251, 0, 231, 0.8), 0 -5px 1px rgba(0, 233, 235, 0.8), 5px 0 1px rgba(0, 242, 14, 0.8), 0 5px 1px rgba(244, 45, 0, 0.8), -5px 0 1px rgba(59, 0, 226, 0.8);
    }
    55% {
      text-shadow: -1px 1px 8px rgba(255, 255, 255, 0.6), 1px -1px 8px rgba(255, 255, 235, 0.7), 0px 0 3px rgba(251, 0, 231, 0.8), 0 0px 3px rgba(0, 233, 235, 0.8), 0px 0 3px rgba(0, 242, 14, 0.8), 0 0px 3px rgba(244, 45, 0, 0.8), 0px 0 3px rgba(59, 0, 226, 0.8);
    }
    90% {
      text-shadow: -1px 1px 8px rgba(255, 255, 255, 0.6), 1px -1px 8px rgba(255, 255, 235, 0.7), -5px 0 1px rgba(251, 0, 231, 0.8), 0 5px 1px rgba(0, 233, 235, 0.8), 5px 0 1px rgba(0, 242, 14, 0.8), 0 -5px 1px rgba(244, 45, 0, 0.8), 5px 0 1px rgba(59, 0, 226, 0.8);
    }
    100% {
      text-shadow: -1px 1px 8px rgba(255, 255, 255, 0.6), 1px -1px 8px rgba(255, 255, 235, 0.7), 5px 0 1px rgba(251, 0, 231, 0.8), 0 -5px 1px rgba(0, 233, 235, 0.8), -5px 0 1px rgba(0, 242, 14, 0.8), 0 5px 1px rgba(244, 45, 0, 0.8), -5px 0 1px rgba(59, 0, 226, 0.8);
    }
  }

  @keyframes type {
    0%,
    19% {
      opacity: 0;
    }
    20%,
    100% {
      opacity: 1;
    }
  }
}
</style>
