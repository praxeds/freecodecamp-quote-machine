<template>
  <nav>
    <section id="circles">
      <span></span>
      <span></span>
      <span></span>
    </section>
    <section id="arrows">
      <Button :icon="chevronBackOutline" />
      <Button :icon="chevronForwardOutline" class="disabled" />
    </section>
    <Button :icon="documentTextOutline" class="more-padding" />
    <div id="searchbar">
      <textarea maxlength="50" placeholder="ChineseProverbs.live"></textarea>
    </div>
  </nav>
</template>

<script>
import Button from "./buttons.vue";
import {
  chevronBackOutline,
  chevronForwardOutline,
  documentTextOutline,
} from "ionicons/icons";

export default {
  name: "Header",
  components: {
    Button,
  },
  setup() {
    return {
      chevronBackOutline,
      chevronForwardOutline,
      documentTextOutline,
    };
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

  section#arrows {
    height: inherit;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 0.2rem;
  }

  .more-padding {
    min-width: 2.5rem;
    margin-left: 1rem;
  }

  #searchbar {
    flex: 0 0 30rem;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 1.6rem;
    padding: 0;
    margin: auto 0 auto 3rem;
    border-radius: 0.3rem;
    border: none;
    background: #fdfdfd;
    box-shadow: 0 2px 1px 0 $medium-gray;

    textarea {
      width: 100%;
      height: 70%;
      border: none;
      background: none;
      text-align: center;
      resize: none;
      overflow: hidden;
      &:focus {
        outline: none;
      }
      &::placeholder {
        color: inherit;
        opacity: 1;
      }
    }
  }
}
</style>
