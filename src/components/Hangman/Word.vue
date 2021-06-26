<template>
  <letter
    v-for="letter in letters"
    :key="letter"
    :letter="letter"
    :chosenLetter="chosenLetter"
    :chosen="hello(letter, chosenLetter)"
  >
    {{ letter }}
  </letter>
  <br />
</template>
<script>
import letter from "./letter.vue";
export default {
  components: {
    letter,
  },
  props: ["chosenLetter", "word"],
  computed: {
    letters() {
      this.hello();
      return this.word.toLowerCase().split("");
    },
  },
  methods: {
    hello(letter, chosen) {
      if (letter == chosen) {
        return true;
      }
    },
  },
};
</script>
