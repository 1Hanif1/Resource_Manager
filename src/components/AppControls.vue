<template>
  <item-container>
    <app-button
      v-for="text in texts"
      :key="text"
      :text="text"
      :active="text === currentActive"
      @click="toggleActive(text)"
    ></app-button>
  </item-container>
</template>

<script>
import AppButton from './UI/AppButton.vue';
import ItemContainer from './UI/ItemContainer.vue';
export default {
  inject: ['activeTab'],
  data() {
    return {
      texts: ['Stored Resources', 'Add Resource'],
      currentActive: this.activeTab,
    };
  },
  components: { ItemContainer, AppButton },
  methods: {
    toggleActive(text) {
      this.currentActive = text;
      this.$emit('selected', text);
    },
  },
};
</script>