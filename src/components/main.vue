<template>
  <main>
    <Header />
    <aside></aside>
  </main>
</template>

<script>
import Header from "./header.vue";

export default {
  name: "Main",
  components: {
    Header,
  },
};
</script>

<style scoped lang="scss">
main {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  border-radius: 0.5rem;
  height: 80vh;
  width: 75vw;
  box-shadow: 0 10px 20px 0 hsla(0, 0%, 0%, 0.4);

  aside {
    width: inherit;
    height: inherit;
    position: absolute;
    left: inherit;
    top: inherit;
    transform: inherit;
    border-radius: inherit;
    background: rgba(255, 255, 255, 0.6);
    backdrop-filter: blur(50px);
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
    z-index: -1;
  }
}
</style>
