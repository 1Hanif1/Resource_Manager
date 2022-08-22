<template>
  <button :class="isActive">{{ text }}</button>
</template>

<script>
export default {
  props: {
    text: String,
    active: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    isActive() {
      if (this.active) return 'button--active';
      else return 'button';
    },
  },
};
</script>

<style scoped>
.button {
  padding: 0.8rem 1.5rem;
  font-size: 1.25rem;
  border: none;
  background: none;
  cursor: pointer;
  color: rgb(255, 126, 79);
}

.button:hover {
  background: rgb(255, 126, 79, 0.25);
}

.button--active {
  padding: 0.8rem 1.5rem;
  font-size: 1.25rem;
  background: rgb(255, 126, 79);
  border: none;
  color: white;
}
</style>