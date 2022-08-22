<template>
  <div class="overlay">
    <item-container>
      <h1>Invalid Input</h1>
      <p>Unfortunately, at least one input value is invalid.</p>
      <p>
        Please check all inputs and make sure you enter at least a few
        characters into each input field.
      </p>
      <div><slot></slot></div>
    </item-container>
  </div>
</template>

<script>
import ItemContainer from './ItemContainer.vue';
export default {
  components: { ItemContainer },
};
</script>

<style scoped>
.overlay {
  background: rgb(0, 0, 0, 0.25);
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

h1 {
  text-align: center;
  padding: 1rem 0rem;
  font-size: 1.6rem;
  background: hsla(16, 100%, 76%, 1);
  color: white;
}
p {
  font-size: 1.4rem;
  margin-block: 2rem;
}
</style>