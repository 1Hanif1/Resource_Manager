<template>
  <item-container>
    <h1>
      {{ title }}
      <app-button text="delete" @click="deleteResource"></app-button>
    </h1>
    <p>{{ desc }}</p>
    <a :href="link">View Resource</a>
  </item-container>
</template>

<script>
import AppButton from './AppButton.vue';
import ItemContainer from './ItemContainer.vue';
export default {
  emits: ['delete'],
  components: { AppButton, ItemContainer },
  props: {
    title: String,
    desc: String,
    link: String,
  },
  methods: {
    deleteResource() {
      this.$emit('delete', this.title);
    },
  },
};
</script>

<style scoped>
h1 {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 1.6rem;
}
p {
  font-size: 1.2rem;
}
a {
  color: rgb(255, 126, 79);
  font-size: 1rem;
}
</style>