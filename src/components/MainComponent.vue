<template>
  <main class="main">
    <h1>Speed-reading</h1>

    <p>
      Let's try out <a href="https://www.example.com">this link.</a>
    </p>

    <p>{{ msg }}</p>

    <CurrentWord :word="currentWord" class="u-mt-2"/>
  </main>
</template>

<script>
import CurrentWord from './CurrentWord.vue';

export default {
  name: 'MainComponent',
  components: {
    CurrentWord,
  },
  data: function() {
    return {
      text: [
        'Hello',
        'world.',
      ],
      position: 1,
    };
  },
  computed: {
    currentWord: function() {
      return this.text[this.position];
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
