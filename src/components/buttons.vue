<template>
  <button>
    <ion-icon :icon=icon />
  </button>
</template>

<script>
import { IonIcon } from '@ionic/vue';

export default {
  name: "Button",
  components: { IonIcon },
  props: ['icon']
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

  ion-icon {
    width: auto;
    height: 80%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: $dark-gray;
    &:hover {
      cursor: pointer;
    }
  }
}
</style>
