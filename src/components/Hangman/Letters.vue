<template>
  <button
    class="text-5xl border md:h-20 md:w-20 h-10 w-10 bg-red-400"
    v-for="letter in alphabet"
    :key="letter"
    @click="emitLetter($event, letter)"
  >
    {{ letter }}
  </button>
</template>
<script>
export default {
  data: () => ({
    alphabet: "abcdefghijklmnopqrstuvwxyz".split(""),
  }),
  methods: {
    emitLetter(e, letter) {
      this.$emit("emittedLetter", letter);
      console.log("emitted " + letter);
      e.target.classList.add("bg-grey-400");
      e.target.classList.remove("bg-red-400");
      e.target.disabled = true;
    },
  },
};
</script>
<style scoped></style>
