<template>
  <section>
    <h2 :class="{ fadeout: disabled }">{{ pinyin }}</h2>
    <h1 :class="{ fadeout: disabled }">{{ proverb }}</h1>
    <h3 :class="{ fadeout: disabled }">{{ translation }}</h3>
    <button @click="fetchNewProverb" title="New quote">
      <ion-icon :icon="reloadOutline"></ion-icon>
    </button>
    <aside>
      <button>
        <ion-icon :icon="logoTwitter"></ion-icon>
      </button>
      <button>
        <a href="https://github.com/praxeds" target="_blank">
            <ion-icon :icon="logoGithub"></ion-icon>
        </a>
      </button>
    </aside>
  </section>
</template>

<script>
import axios from "axios";
import { reloadOutline, logoTwitter, logoGithub } from "ionicons/icons";
export default {
  name: "Quote",
  data() {
    return {
      proverb: null,
      pinyin: null,
      translation: null,
      disabled: false,
    };
  },
  setup() {
    return {
      reloadOutline,
      logoTwitter,
      logoGithub,
    };
  },
  methods: {
    async fetchProverb() {
      await axios
        .get("https://chinese-proverbs.onrender.com/api/proverbs/random")
        .then(
          (response) => (
            (this.proverb = response.data.proverb),
            (this.pinyin = response.data.pinyin),
            (this.translation = response.data.translation)
          )
        );
    },
    fetchNewProverb() {
      this.fetchProverb();
      this.disabled = true;
      setTimeout(() => {
        this.disabled = false;
      }, 2000);
    },
  },
  beforeMount() {
    this.fetchProverb();
  },
};
</script>

<style scoped lang="scss">
// Colors
$medium-gray: #b6b5b6;

section {
  height: inherit;
  width: inherit;
  position: absolute;
  left: inherit;
  top: inherit;
  transform: inherit;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  pointer-events: none;

  > * {
    margin: 0;
    text-align: center;
  }

  h1 {
    font-size: 4rem;
    font-weight: 400;
    margin-bottom: 0.7rem;
  }

  h2 {
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: inherit;
    font-size: 1rem;
    font-weight: 500;
    word-spacing: 2.2rem;
  }

  button {
    margin: 0;
    border: none;
    border-radius: 0.3rem;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #fdfdfd;
    box-shadow: 0 2px 1px 0 $medium-gray;
    pointer-events: all;
    transition: all 0.2s ease-in-out;
    &:hover {
      background: #151515;
      cursor: pointer;
      ion-icon {
        color: #fdfdfd;
      }
    }
    ion-icon {
      width: 1rem;
      height: 1rem;
    }
  }

  > button {
    position: absolute;
    bottom: 0;
    right: 0;
    margin: 0 1rem 1rem 0;
  }

  aside {
    position: absolute;
    bottom: 0;
    left: 0;
    margin: 0 0 1rem 1rem;
    display: flex;
    gap: 0.5rem;
  }
}

.fadeout {
  animation: fadeout 2s ease;
}

@keyframes fadeout {
  0% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
