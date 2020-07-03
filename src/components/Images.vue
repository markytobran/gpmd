<template>
  <div classs="images-div">
    <div v-for="(item, index) in image" :key="index">
      <img :src="image[index].urls.small" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Images",
  data() {
    return {
      image: [],
    };
  },
  methods: {
    getImages() {
      axios
        .get(
          "https://api.unsplash.com/photos/?client_id=nx_5QGkFaJUNL_XVzPLKCxd8dW2hPzvsvqoWXRcXkNA"
        )
        .then((response) => (this.image = response.data))
        .catch((err) => {
          console.log("error", err);
        });
    },
  },
  created() {
    this.getImages();
  },
};
</script>
<style></style>
