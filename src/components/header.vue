<template>
  <nav>
    <section id="circles">
      <span></span>
      <span></span>
      <span></span>
    </section>
    <Button :icon="chevronBackOutline"/>
  </nav>
</template>

<script>
import Button from "./buttons.vue";
import { chevronBackOutline } from 'ionicons/icons';

export default {
  name: "Header",
  components: {
    Button,
  },
  setup() {
    return {
      chevronBackOutline
    }
  },
};
</script>

<style scoped lang="scss">
// Colors
$red: #fc615c;
$yellow: #fdbe40;
$green: #34ca49;
$medium-gray: #b6b5b6;

$transition: all 0.2s ease-in-out;

nav {
  display: flex;
  height: 2.5rem;
  border-radius: 0.5rem 0.5rem 0 0;
  border-bottom: 1px solid $medium-gray;
  background: linear-gradient(#eeeeee, #d7d6d7);

  section#circles {
    flex: 0 0 6rem;
    padding: 0 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;

    span {
      height: 1rem;
      width: 1rem;
      border-radius: 50%;
      transition: $transition;
      &:nth-of-type(1) {
        background: $red;
      }
      &:nth-of-type(2) {
        background: $yellow;
      }
      &:nth-of-type(3) {
        background: $green;
      }
      &:hover {
        cursor: pointer;
        filter: brightness(90%);
      }
    }
  }
}
</style>
