<template>
  <section>
    <h2 :class="{ fadeout: disabled }">{{ pinyin }}</h2>
    <h1 :class="{ fadeout: disabled }">{{ proverb }}</h1>
    <h3 :class="{ fadeout: disabled }">{{ translation }}</h3>
    <button @click="fetchNewProverb">Click me</button>
  </section>
</template>

<script>
import axios from "axios";
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
      this.disabled = true;
      this.fetchProverb();
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
    &::before {
      content: "“";
      font-size: 6rem;
      font-weight: 700;
      margin-right: 0.5rem;
    }
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
    padding: 1.5rem 4.5rem;
    border: none;
    border-radius: 0.3rem;
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    justify-content: center;
    align-items: center;
    background: #fdfdfd;
    box-shadow: 0 2px 1px 0 $medium-gray;
    pointer-events: all;

    &:hover {
      background: #333;
      cursor: pointer;
      color: #f1f1f1;
    }
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
