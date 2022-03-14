<script>
import HotImage from "../components/HotImage.vue";
import Navbar from "../components/Navbar.vue";
import axios from "axios";

export default {
  name: "HotView",
  components: {
    HotImage,
    Navbar,
  },
  data() {
    return {
      loading: true,
      images: null,
      errored: false,
    };
  },
  //Get Memes Via Meme Api
  mounted() {
    axios
      .get("https://meme-api.herokuapp.com/gimme/memes/4")
      .then((response) => {
        console.log(response.data);
        this.images = response.data["memes"];
      })
      .catch((error) => {
        console.log(error);
        this.errored = true;
      })
      .finally(() => (this.loading = false));
  },
};
</script>

<template>
  <div class="container py-4">
    <navbar></navbar>
    <h1>Hottest Memes of the Week</h1>

    <h3>Hot Memes</h3>
    <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 g-3" v-if="images">
      <!-- Call Image component and sync with data -->
      <hot-image
        v-for="image in images"
        v-bind:image="image"
        v-bind:key="image.postLink"
        v-bind:imageTitle="image.title"
        v-bind:imageSrc="image.url"
        v-bind:imageAlt="'From r/' + image.subreddit"
        v-bind:imageDescription="
          'Made by: ' + image.author + 'on r/' + image.subreddit
        "
      >
      </hot-image>
    </div>
  </div>
</template>
