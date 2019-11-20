<template>
  <p class="word-stats">
    Words: {{ current }}/{{ total }}<br>
    Time: {{ seconds }} seconds
  </p>
</template>

<script>
export default {
  name: 'WordStats',
  props: {
    current: Number,
    total: Number,
    time: Number,
  },
  computed: {
    seconds() {
      return Math.round(this.time / 1000);
    }
  },
};
</script>

<style>
.word-stats {
}
</style>
