<template>
  <Main/>
</template>

<script>
import Main from './components/main.vue'

export default {
  name: 'App',
  components: {
    Main
  }
}
</script>

<style lang="scss">
// Colors
$color-primary: #0f0f0f;
$color-primary-light: #b7b7b7;

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100vh;
  // Trocar background depoisss
  background: url("./assets/pexels-eberhard-grossgasteiger-1287145.jpg");
  background-size: cover;
  background-position: center;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $color-primary;
}
</style>
