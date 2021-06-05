<template>
  <div class="background">
    <div class="container">
      <img src="@/assets/icons/question_dark.svg" class="fe-button" />
      <img src="@/assets/icons/sound_on_dark.svg" class="volume fe-button" />
    </div>
    <div class="section_first">
      <h1 class="animate__animated animate__zoomIn">Финский эпос</h1>
      <span>Окунитесь в сказочный мир Финляндии</span>
      <div class="down">
        <h3>Листайте вниз для продолжения</h3>
        <a href="#creatures" class="arrow fe-button">
          <img src="@/assets/icons/down.svg" />
        </a>
      </div>

      <div class="section_main" id="creatures">
        <div id="app">
          <v-carusel :carusel_data="sliderItems" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import vCarusel from "./components/v-carusel";

export default {
  name: "app",
  components: {
    vCarusel,
  },
  data() {
    return {
      sliderItems: [
        { id: 1, name: "witch", img: "witch_card.jpg", img_info: "witch.jpg" },
        { id: 2, name: "snake", img: "Snake_card.jpg", img_info: "Snake.jpeg" },
        { id: 3, name: "img3", img: "witch_card2.jpg", img_info: "witch.jpg" },
      ],
    };
  },
  /*mounted: function() {
    setTimeout(() => {
      // document.getElementById('fe-loading').remove();
    }, 5 * 1000)
  } */
};
</script>


<style lang="scss">

:root {
  --bg-color: #0f0f0e;
  --primary-color: #af8d51;
  --text-color: #af8d51;
  --gold-dark: #60502f;
  --indent: 40px;
}

html {
  scroll-behavior: smooth;
}

body {
  background-image: url(assets/main-back.png);
  background-size: cover;
  background-repeat: no-repeat;
  background-color: var(--bg-color);
  scroll-behavior: smooth;
  object-fit: cover;
  margin: 0;
  user-select: none;
}

.fe-button {
  cursor: pointer;
}

#app {
  font-family: Arial;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: greyscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 50vh;
}

.background {
  font-weight: bold;
  text-align: center;
  color: var(--text-color);
  font-family: Galaktika, sans-serif;
  letter-spacing: 0.2em;
}

.section_first h1 {
  letter-spacing: 0.2em;

  line-height: 72px;
}

.container {
  top: 3vh;
  right: 3vh;
  position: fixed;
}

.container img {
  width: 50px;
  height: 50px;
  z-index: 100;
}

.section_first {
  height: 40vh;
}

.section_first span {
  margin: 0;
  height: 10vh;
  display: block;
  font-size: 200%;
  font-family: "Oswald";
  color: #60502f00;
  animation: text-info 3s 1;
  animation-delay: 3s;
  animation-fill-mode: forwards;
}

.section_first h1 {
  margin-top: 30vh;
  height: 10vh;
  font-size: 350%;
}

.arrow {
  width: 50px;
  height: 50px;
  align-items: center;
  animation: Appearance 3s 1;
  animation-duration: 13s;
  animation-timing-function: cubic-bezier(0.1, -0.6, 0.2, 0);
}

.down {
  margin-top: 25vh;
  height: 10vh;
}

.down h3 {
  font-family: "Oswald", sans-serif;
  letter-spacing: 0.2em;
  color: rgba(35, 36, 20, 0);
  animation: text-down 3s 1;
  animation-delay: 4s;
  animation-fill-mode: forwards;
  animation-timing-function: ease-out;
}

.animate__animated.animate__zoomIn {
  --animate-duration: 3s;
}

@keyframes text-down {
  0% {
    color: #60502f00;
  }
  50% {
    color: #3d33207e;
  }
  100% {
    color: #3d3320;
  }
}

@keyframes text-info {
  0% {
    color: rgba(110, 99, 70, 0);
  }
  50% {
    color: rgba(110, 99, 70, 0.5);
  }
  100% {
    color: rgba(110, 99, 70, 1);
  }
}

@keyframes Appearance {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.section_main {
  margin-top: 85vh;
  scroll-margin-block-end: inherit;
}
</style>
