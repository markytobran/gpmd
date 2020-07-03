<template>
  <header>
    <h1>Frontend coding challenge</h1>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header {
  display: flex;
  padding: 3rem;
  justify-content: center;
  align-items: center;
}

h1 {
  font-size: 3rem;
  color: #fff;
  text-shadow: 1rem 1rem 1rem rgba(#000, 0.5);
}
</style>
