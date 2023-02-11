<template>
  <nav>
    <section id="left">
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
    </section>
    <div id="searchbar">
      <textarea maxlength="50" placeholder="ChineseProverbs.live"></textarea>
      <ion-icon :icon="refreshOutline"></ion-icon>
    </div>
    <section id="right">
      <Button :icon="shareOutline" class="more-padding" />
      <Button :icon="copyOutline" class="more-padding" />
      <div>
        <ion-icon :icon="addOutline"></ion-icon>
      </div>
    </section>
  </nav>
</template>

<script>
import Button from "./buttons.vue";
import { ionicons } from "@ionic/vue";
import {
  chevronBackOutline,
  chevronForwardOutline,
  documentTextOutline,
  shareOutline,
  copyOutline,
  addOutline,
  refreshOutline,
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
      shareOutline,
      copyOutline,
      addOutline,
      refreshOutline,
    };
  },
};
</script>

<style scoped lang="scss">
// Colors
$red: #fc615c;
$yellow: #fdbe40;
$green: #34ca49;
$dark-gray: #5b5b5b;
$medium-gray: #b6b5b6;

$transition: all 0.2s ease-in-out;

nav {
  display: flex;
  gap: 1rem;
  height: 2.5rem;
  border-radius: 0.5rem 0.5rem 0 0;
  border-bottom: 1px solid $medium-gray;
  background: linear-gradient(#eeeeee, #d7d6d7);

  > section {
    flex: 1;
    flex-shrink: 0;
    display: flex;
    align-items: center;

    .more-padding {
      min-width: 2.5rem;
    }

    &#left {
      justify-content: flex-start;
      gap: 0.5rem;
      padding-left: 1rem;

      section#circles {
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 0.3rem;

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
    }

    &#right {
      justify-content: flex-end;
      gap: 0.5rem;

      > div {
        align-self: end;
        display: inherit;
        justify-content: center;
        align-items: inherit;
        width: 1.4rem;
        height: 1.4rem;
        color: $dark-gray;
        background-color: #d1d0d1;
        border-top: 1px solid $medium-gray;
        border-left: 1px solid $medium-gray;
      }
    }
  }

  #searchbar {
    flex: 2;
    display: flex;
    align-self: center;
    justify-self: center;
    justify-content: center;
    align-items: center;
    height: 1.6rem;
    padding: 0 0.4rem;
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

    ion-icon {
      color: $dark-gray;
      font-size: 1.2rem;
      margin-left: 0.2rem;
      &:hover {
        cursor: pointer;
      }
    }
  }
}
</style>
