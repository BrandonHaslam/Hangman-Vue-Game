<template>
  <Word :word="word" :chosenLetter="currentLetter" />
  <Letters @emittedLetter="doSomething" />
</template>
<script>
import Letters from "./Letters.vue";
import Word from "./Word.vue";
export default {
  name: "Hangman",
  components: {
    // Hungman,
    Word,
    Letters,
  },
  data: () => ({
    currentLetter: "",
    word: "Arbiter",
  }),
  methods: {
    doSomething(letter) {
      this.currentLetter = letter;
      console.log(letter + " from child");
    },
  },
};
</script>
