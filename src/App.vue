<template>
  <app-title></app-title>
  <app-controls @selected="setCurrentTab"></app-controls>
  <div v-if="getCurrentTab === 'Stored Resources'">
    <app-resource
      v-for="res in resources"
      :key="res.title"
      :title="res.title"
      :desc="res.desc"
      :link="res.link"
      @delete="removeResource(res.title)"
    ></app-resource>
  </div>
  <app-form
    v-else-if="getCurrentTab === 'Add Resource'"
    @new-data="addData"
  ></app-form>
</template>

<script>
import AppTitle from './components/AppTitle.vue';
import AppControls from './components/AppControls.vue';
import AppResource from './components/UI/AppResource.vue';
import AppForm from './components/AppForm.vue';
export default {
  components: { AppTitle, AppControls, AppResource, AppForm },
  provide() {
    return { activeTab: this.currentTab };
  },
  data() {
    return {
      currentTab: 'Stored Resources',
      resources: [
        {
          title: 'Official Vue Guide',
          desc: 'Official Vue.js Documentation.',
          link: 'https://vuejs.org/',
        },
        {
          title: 'W3Schools TypeScript',
          desc: 'Learn the basics of typescript.',
          link: 'https://www.w3schools.com/typescript/',
        },
      ],
    };
  },
  computed: {
    getCurrentTab() {
      return this.currentTab;
    },
  },
  methods: {
    removeResource(title) {
      this.resources = this.resources.filter((res) => res.title !== title);
    },
    setCurrentTab(tab) {
      this.currentTab = tab;
    },
    addData(newData) {
      this.resources.push(newData);
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
*,
*::after,
*::before {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-size: 62.5%;
  font-family: 'Poppins', sans-serif;
}
a,
a:visited,
a:focus {
  text-decoration: none;
  color: black;
}

input {
  display: block;
}
</style>