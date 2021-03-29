<template>
  <h1>Reaction Timer mini</h1>
  <button id="start-button" @click="start">Play</button>
  <Block v-if="isPlaying" />
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
      console.log(this.delay);
    },
  },
};
</script>

<style>
body {
  background-color: #a9a9a9;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}

button {
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

#start-button:hover {
  color: #000;
}
</style>
