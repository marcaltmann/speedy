<template>
  <main class="main">
    <h1>Speed-reading</h1>

    <p>
      Let's try out <a href="https://www.example.com">this link.</a>
    </p>

    <p>{{ msg }}</p>

    <CurrentWord :word="currentWord" class="u-mt-4"/>
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
  data: function() {
    return {
      text: 'Der US-Diplomat Gordon Sondland ist der entscheidende Mann in den Impeachment-Untersuchungen. Er könnte Donald Trump direkt belasten. Doch wird er umfassend aussagen?',
      position: 0,
    };
  },
  computed: {
    words: function() {
      return this.text.split(' ');
    },
    currentWord: function() {
      return this.words[this.position];
    },
  },
  mounted: function() {
    let id = setInterval(() => {
      if (this.position === this.words.length - 1) {
        clearInterval(id);
      } else {
        this.position += 1;
      }
    }, INTERVAL);
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
