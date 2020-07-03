<template v-if="image.length > 10">
  <div class="images-div">
    <figure v-for="(item, index) in image" :key="index">
      <div class="images-div-figure">
        <div class="images-div-picture">
          <a :href="image[index].links.html" target="_blank">
            <img
              :src="image[index].urls.small"
              :alt="image[index].alt_description"
            />
            <h5>Author: {{ image[index].user.first_name }}</h5>
          </a>
        </div>
        <div class="images-div-icons">
          <ul>
            <li><i class="far fa-heart"></i></li>
            <li><i class="fas fa-location-arrow"></i></li>
            <li><i class="fas fa-comments"></i></li>
          </ul>
        </div>
        <small>{{ image[index].likes }} likes</small>
      </div>
    </figure>
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
<style scoped lang="scss">
//Variables
$color-black: #000;
$color-white: #fff;

img {
  height: 400px;
  width: 450px;
  margin-bottom: 2rem;
  cursor: pointer;
  box-shadow: 0 2rem 2rem (rgba($color-black, 0.4));
  transition: all 1s;

  &:hover {
    filter: brightness(0.3);
  }
  &:hover ~ h5 {
    opacity: 1;
    transform: translateY(40px);
  }
}

small {
  font-weight: 800;
  color: $color-white;
  font-size: 2rem;
}

i {
  font-size: 2rem;
  cursor: pointer;
}

.images-div {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 5px;
  box-sizing: border-box;
  padding: 10px;
  margin: 0 auto;

  &-figure {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    cursor: pointer;
  }
  &-picture {
    position: relative;

    & h5 {
      position: absolute;
      top: 0%;
      left: 2rem;
      color: $color-white;
      font-size: 2rem;
      opacity: 0;
      margin-left: auto;
      margin-right: auto;
      transition: all 0.3s;
    }
  }
  &-icons ul {
    display: flex;
    flex-direction: row;

    & li {
      list-style-type: none;
      padding: 0 1rem;
      color: #ffc0cb;
    }
  }
}
@media screen and (max-width: 1800px) {
  .images-div {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
  }
}

@media screen and (max-width: 1280px) {
  .images-div {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
  }
  img {
    height: 300px;
    width: 300px;
    margin-bottom: 1rem;
  }
}

@media screen and (max-width: 700px) {
  .images-div {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
  }
  img {
    height: 300px;
    width: 300px;
    margin-bottom: 1rem;
  }
}
</style>
