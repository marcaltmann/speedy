<template>
  <div id="app">
    <MainComponent/>
  </div>
</template>

<script>
import MainComponent from './components/MainComponent.vue';

export default {
  name: 'app',
  components: {
    MainComponent,
  },
};
</script>

<style lang="scss">
$base-unit: 1.5rem;

body {
  background-color: #f0f0f0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.u-mt-1 {
  margin-top: 1.5rem;
}

.u-mt-2 {
  margin-top: 3rem;
}

.u-mt-3 {
  margin-top: 4.5rem;
}

.u-mt-4 {
  margin-top: 6rem;
}

</style>
