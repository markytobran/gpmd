<template>
  <div id="app">
    <Header></Header>
    <Images></Images>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "../src/components/Header";
import Images from "../src/components/Images";
import Footer from "../src/components/Footer";

export default {
  name: "App",
  components: {
    Header,
    Images,
    Footer,
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;800&display=swap");

* {
  padding: 0;
  margin: 0;
}

*,
*::after,
*::before {
  box-sizing: inherit;
}

html {
  font-size: 62.5%;
  box-sizing: border-box;
}

body {
  font-family: "Montserrat", sans-serif;
  background: linear-gradient(to right bottom, #eee, #000);
  line-height: 1.6;
  background-size: 100% 100%;
  padding: 2rem;
}
</style>
