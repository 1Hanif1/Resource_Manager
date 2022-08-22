<template>
  <item-container>
    <p>Title</p>
    <input type="text" v-model="title" />
    <p>Description</p>
    <textarea v-model="desc"></textarea>
    <p>Link</p>
    <input type="text" v-model="link" />
    <app-button text="Add Resource" @click="addResource"></app-button>
  </item-container>
  <teleport to="body">
    <app-modal v-if="showModal">
      <app-button @click="hideModal" text="Okay"></app-button
    ></app-modal>
  </teleport>
</template>

<script>
import ItemContainer from './UI/ItemContainer.vue';
import AppButton from './UI/AppButton.vue';
import AppModal from './UI/AppModal.vue';
export default {
  components: { ItemContainer, AppButton, AppModal },
  emits: ['new-data'],
  data() {
    return {
      showModal: false,
      title: '',
      desc: '',
      link: '',
    };
  },
  methods: {
    addResource() {
      let inputEmpty = [this.title, this.desc, this.link].some(
        (input) => input === ''
      );
      if (inputEmpty) {
        this.showModal = true;
        return;
      }
      let newData = {
        title: this.title,
        desc: this.desc,
        link: this.link,
      };
      this.$emit('new-data', newData);
    },
    hideModal() {
      this.showModal = false;
    },
  },
};
</script>

<style scoped>
p {
  font-size: 1.6rem;
  font-weight: bold;
}
input,
textarea {
  margin-block: 1rem;
  width: 100%;
  outline: none;
  font-size: 1.6rem;
}
input {
  height: 2rem;
}
textarea {
  height: 4rem;
}
input:focus,
textarea:focus {
  border-color: hsla(16, 100%, 76%, 1);
  background: hsla(16, 100%, 76%, 0.5);
}
</style>