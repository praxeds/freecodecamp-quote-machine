<template>
  <section>
    <h1>{{ proverb }}</h1>
    <h2>{{ pinyin }}</h2>
    <h3>{{ translation }}</h3>
  </section>
</template>

<script>
import axios from "axios";
export default {
  name: "Quote",
  data() {
    return {
      proverb: null,
    };
  },
  methods: {
    async fetchProverb() {
      axios
        .get("https://chinese-proverbs.onrender.com/api/proverbs/random")
        .then(
          (response) => (
            (this.proverb = response.data.proverb),
            (this.pinyin = response.data.pinyin),
            (this.translation = response.data.translation)
          )
        );
    },
  },
  beforeMount() {
    this.fetchProverb();
  },
};
</script>

<style scoped lang="scss">
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

  h1,h2,h3 {
    margin: 0;
  }

  button {
    margin-left: 1rem;
    padding: 0.5rem 1rem;
    border: none;
    border-radius: 0.5rem;
    background: #f1f1f1;
    color: #333;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s ease-in-out;

    &:hover {
      background: #333;
      color: #f1f1f1;
    }
  }
}
</style>
