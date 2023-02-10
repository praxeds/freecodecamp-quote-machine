<template>
  <main>
    <Header />
    <h1>teste</h1>
    <h3>Essa é a página principal</h3>
    <p>
      Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sapiente
      necessitatibus repudiandae ipsam vero. Aliquam eos, ipsam provident minima
      enim obcaecati error nihil perferendis, quia quaerat non, vero dicta
      voluptas iure deleniti placeat hic veritatis ut odio dolor consectetur
      quos eius.
    </p>
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
  backdrop-filter: blur(50px);
  background: rgba(255, 255, 255, 0.6);
  backdrop-filter: blur(5px);
  -webkit-backdrop-filter: blur(5px);
  border: 1px solid rgba(255, 255, 255, 0.3);
  box-shadow: 0 10px 30px 0 hsla(0, 0%, 0%, 0.4);
}
</style>
