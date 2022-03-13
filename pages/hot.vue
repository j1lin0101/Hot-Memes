<script>
import HotImage from "../components/HotImage.vue";

export default {
  name: "HotView",
  components: {
    HotImage,
  },
  data() {
    return {
      // Image Data - Title, Description, Image, URL
      images: [
        {
          id: 1,
          src: "~/assets/images/ceo.jpg",
          title: "CEO Meme",
          alt: "A meme with various popular CEOs",
          description: "A meme with various popular CEOs",
        },
        {
          id: 2,
          src: "~/assets/images/2010/knee.jpeg",
          title: "Arrow to the Knee",
          alt: "A classic meme of taking an arrow to the knee",
          description: "A classic meme of taking an arrow to the knee",
        },
        {
          id: 3,
          src: "~/assets/images/2010/morpheus.jpeg",
          title: "Morpheus",
          alt: "A classic meme of the Matrix's Morpheus",
          description: "A classic meme of the Matrix's Morpheus",
        },
      ],
    };
  },
};
</script>

<template>
  <div class="container py-4">
    <b-nav pills class="pb-3 mb-4 border-bottom">
      <b-nav-item to="/">Home</b-nav-item>
      <b-nav-item to="/hot">Hot</b-nav-item>
      <b-nav-item to="/about">About</b-nav-item>
      <b-nav-item to="/archive">Archive</b-nav-item>
    </b-nav>
    <h1>Hottest Memes of the Week</h1>

    <h3>Hot Memes</h3>
    <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 g-3" v-if="images">
      <!-- Call Image component and sync with data -->
      <hot-image
        v-for="image in images"
        v-bind:image="image"
        v-bind:key="image.id"
        v-bind:imageTitle="image.title"
        v-bind:imageSrc="image.src"
        v-bind:imageAlt="image.alt"
        v-bind:imageDescription="image.description"
      >
      </hot-image>
    </div>
  </div>
</template>
