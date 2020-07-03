<template>
  <footer>
    <a href="#">TOP</a>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped lang="scss">
footer {
  margin-top: 5rem;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

a {
  border-radius: 100px;
  color: white;
  background-color: #ffc0cb;
  padding: 5px 4rem;
  text-decoration: none;
  font-size: 2rem;
  font-weight: 800;
  animation: top 1s infinite;
}

@keyframes top {
  0% {
    transform: translate(0px, 0px) rotate(0deg);
  }
  25% {
    transform: translate(0px, 10px) rotate(0deg);
  }
  50% {
    transform: translate(0px, 5px) rotate(0deg);
  }
  75% {
    transform: translate(0px, 15px) rotate(0deg);
  }
  100% {
    transform: translate(0px, 0px) rotate(0deg);
  }
}
</style>
