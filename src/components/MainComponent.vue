<template>
  <main class="main">
    <h1>Speed-reading</h1>

    <CurrentWord :word="currentWord" class="u-mt-4"/>

    <button v-on:click="startTimer" type="button" class="u-mt-4">
      Start
    </button>

    <WordStats :current="currentWordPosition" :total="totalWords"
      class="u-mt-1"/>
  </main>
</template>

<script>
import CurrentWord from './CurrentWord.vue';
import WordStats from './WordStats.vue';

const INTERVAL = 200; // milliseconds

export default {
  name: 'MainComponent',
  components: {
    CurrentWord,
    WordStats,
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
    currentWordPosition() {
      return this.position + 1;
    },
    totalWords() {
      return this.words.length;
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
