<template>
  <main class="main">
    <h1>Speed-reading</h1>

    <p>
      Let's try out <a href="https://www.example.com">this link.</a>
    </p>

    <p>{{ msg }}</p>

    <CurrentWord :word="currentWord" class="u-mt-4"/>

    <button v-on:click="startTimer" type="button" class="u-mt-4">
      Start
    </button>
  </main>
</template>

<script>
import CurrentWord from './CurrentWord.vue';

const INTERVAL = 200; // milliseconds

export default {
  name: 'MainComponent',
  components: {
    CurrentWord,
  },
  data() {
    return {
      text: 'Der US-Diplomat Gordon Sondland ist der entscheidende Mann in den Impeachment-Untersuchungen. Er könnte Donald Trump direkt belasten. Doch wird er umfassend aussagen?',
      position: 0,
    };
  },
  computed: {
    words() {
      return this.text.split(' ');
    },
    currentWord() {
      return this.words[this.position];
    },
  },
  intervalId: null,
  methods: {
    startTimer() {
      if (this.intervalId) {
        clearInterval(this.intervalId);
      }
      this.position = 0;
      this.intervalId = setInterval(() => {
        if (this.position === this.words.length - 1) {
          clearInterval(this.intervalId);
          this.intervalId = null;
        } else {
          this.position += 1;
        }
      }, INTERVAL);
    },
  },
  mounted() {
    this.startTimer();
  },
  props: {
    msg: String,
  },
};
</script>

<style>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
