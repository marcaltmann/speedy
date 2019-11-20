<template>
  <p class="current-word">
    {{ word }}
  </p>
</template>

<script>
export default {
  name: 'CurrentWord',
  props: {
    word: String,
  },
};
</script>

<style lang="scss">
$current-word-font-size: 4rem;

.current-word {
  font-size: $current-word-font-size;
  line-height: 6rem;
  min-height: 6rem;
}
</style>
