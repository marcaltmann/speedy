<template>
  <p class="word-stats">
    Words: {{ current }}/{{ total }}
  </p>
</template>

<script>
export default {
  name: 'WordStats',
  props: {
    current: Number,
    total: Number,
  },
};
</script>

<style>
.word-stats {
}
</style>
