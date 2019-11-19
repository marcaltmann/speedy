<template>
  <p class="current-word">
    {{ word }}
  </p>
</template>

<script>
export default {
  name: 'CurrentWord',
  data: function() {
    return {
      word: 'Hello',
    };
  },
};
</script>

<style>
.current-word {
  font-size: 4rem;
  line-height: 6rem;
}
</style>
