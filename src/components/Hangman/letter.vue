<template>
  <span
    :id="letter"
    class="text-9xl letter relative m-1 flex-1 inline-block"
    :class="[active ? 'text-black' : 'text-transparent']"
  >
    <slot></slot>
  </span>
</template>
<script>
export default {
  name: "letter",
  props: ["chosen"],
  data: () => ({
    lock: false,
  }),
  computed: {
    active() {
      if (this.chosen == true) {
        this.change();
        return true;
      } else if (this.lock == false) {
        return false;
      } else {
        return true;
      }
    },
  },
  methods: {
    change() {
      this.lock = true;
    },
  },
};
</script>
<style scoped>
.letter::after {
  content: " ";
  display: block;
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 1px;
  background-color: #000;
  /* opacity: 100 !important; */
}
</style>
