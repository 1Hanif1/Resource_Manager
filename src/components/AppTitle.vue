<template>
  <header>
    <h1>My Learning Resources</h1>
  </header>
</template>

<style scoped>
header {
  width: 100%;
  padding: 2em 0em;
  background: hsla(16, 100%, 76%, 1);
  background: linear-gradient(
    135deg,
    hsla(16, 100%, 76%, 1) 0%,
    hsla(49, 100%, 81%, 1) 100%
  );
}
h1 {
  text-align: center;
  font-size: 3rem;
  color: white;
  text-shadow: 0em 0.05em rgba(0, 0, 0, 0.25);
}
@media screen and (max-width: 800px) {
  h1 {
    font-size: 1.4rem;
  }
}
</style>