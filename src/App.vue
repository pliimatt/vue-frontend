<template>
  <div class="App">
    <CV />
    <button @click="showIdleGame = !showIdleGame">Show game</button>
    <idle-game-comp v-if="showIdleGame" />
  </div>
</template>

<script>
import CV from "./components/CV";
import IdleGameComp from "./components/IdleGameComp.vue";
import "./assets/App.css";
import "./assets/index.css";
import "./assets/IdleGame.css";

export default {
  name: "App",
  components: {
    CV,
    IdleGameComp,
  },
  data() {
    return {
      showIdleGame: false,
    };
  },
};
</script>