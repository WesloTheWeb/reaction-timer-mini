<template>
  <h1>Reaction Timer Mini</h1>
  <div id="instructions">
    <h2>Instructions</h2>
    Welcome to a reaction test.
    <ul>
      <li>To begin click the 'Play' button.</li>
      <li>
        A red button will show at a time and you must click it to test your
        reaction.
      </li>
      <li>
        Afterwards, it will show how fast you reacted. Click Reset to reset and
        try again.
      </li>
    </ul>
  </div>
  <div id="timer-button-container">
    <button id="start-button" @click="start" :disabled="isPlaying">Play</button>
    <button id="reset-button" @click="reset" v-if="isPlaying">Reset</button>
  </div>
  <Block v-if="isPlaying" :delay="delay" />
</template>

<script>
import Block from "./components/Block.vue";

export default {
  name: "App",
  components: { Block },

  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },

  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000; // gets us a random amount of miliseconds.
      this.isPlaying = true;
    },

    reset() {
      this.isPlaying = false;
    },
  },
};
</script>

<style>
:root {
  --clear: crimson;
  --click: #6bc6ff;
  --white: #ffffff;
  --backgroundColor: #a9a9a9;
}

body {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  background-color: var(--backgroundColor);
  color: #444;
  margin: 0 auto;
}

h1 {
  border-bottom: 2px solid #000;
  padding-bottom: 1rem;
  text-align: center;
}

#instructions {
  padding: 0 2rem;
  margin: 2rem 0;
}

#timer-button-container {
  text-align: center;
}

#timer-button-container button {
  margin: 0 1.5rem;
}

button {
  background-color: var(--click);
  font-weight: bold;
  font-size: 1.5rem;
  padding: 1rem;
  border-radius: 10px;
}

button:hover {
  cursor: pointer;
  filter: brightness(85%);
}

#start-button {
  background-color: limegreen;
  color: #fff;
}

#start-button:hover,
#reset-button:hover {
  color: #000;
}

#start-button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

#reset-button {
  background-color: var(--clear);
  color: var(--white);
}
</style>