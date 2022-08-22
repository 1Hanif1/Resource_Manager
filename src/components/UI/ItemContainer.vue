<template>
  <div class="container">
    <slot></slot>
  </div>
</template>

<style scoped>
.container {
  width: 30%;
  margin: 0 auto;
  padding: 1rem;
  border-radius: 0.5rem;
  margin-block: 2rem;
  box-shadow: 0rem 0rem 0.25rem hsl(0, 0%, 0%, 0.25);
  background-color: white;
}
@media screen and (max-width: 1400px) {
  .container {
    width: 60%;
  }
}
@media screen and (max-width: 800px) {
  .container {
    width: 90%;
  }
}
</style>