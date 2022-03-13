<template>
  <div :class="transform">
    <svg
      @mouseenter="$emit('select', number)"
      @mouseleave="$emit('select', null)"
      class="top"
      width="128"
      height="83"
      viewBox="0 0 284 183"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <rect width="284" height="183" rx="45" fill="#B63C46" />
      <path
        d="M143.833 154.333V29M143.833 29L89 83.8333M143.833 29L198.667 83.8333"
        stroke="#FFA858"
        stroke-width="20"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
      <path
        d="M143.833 150.333V25M143.833 25L89 79.8333M143.833 25L198.667 79.8333"
        stroke="#FB8B24"
        stroke-width="20"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
  </div>
</template>

<script>
export default {
  props: ["number"],
  computed: {
    transform() {
      switch (+this.number) {
        case 0:
          return "deg0";
        case 1:
          return "deg90";
        case 2:
          return "deg180";
        case 3:
          return "degm90";
      }
    },
  },
  methods: {
    leave() {
      console.log(null);
    },
  },
};
</script>

<style scoped>
.top {
  cursor: pointer;
}
</style>
