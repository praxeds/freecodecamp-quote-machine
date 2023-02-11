<template>
  <button>
  </button>
</template>

<script>

export default {
  name: "Button",
  props: ['oi'],
};
</script>

<style lang="scss">
// Colors
$dark-gray: #5b5b5b;
$medium-gray: #b6b5b6;

button {
  min-width: 2rem;
  height: 1.7rem;
  padding: 0;
  margin: auto 0;
  border-radius: 0.3rem;
  border: none;
  background: #fdfdfd;
  box-shadow: 0 2px 1px 0 $medium-gray;

  div.ion {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    &:hover {
      cursor: pointer;
    }

    svg {
      width: auto;
      height: 1.6rem;
      fill: $dark-gray;
    }
  }
}
</style>
