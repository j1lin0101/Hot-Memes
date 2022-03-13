<template>
  <div class="container py-4">
    <b-nav pills class="pb-3 mb-4 border-bottom">
      <b-nav-item to="/">Home</b-nav-item>
      <b-nav-item to="/hot">Hot</b-nav-item>
      <b-nav-item to="/about">About</b-nav-item>
      <b-nav-item to="/archive">Archive</b-nav-item>
    </b-nav>
    <h1>Legendary Memes from a Simpler Time</h1>
    <img src="/assets/logo.png" alt="" />
    <div class="container">
      <div class="row">
        <div class="col col-lg-12">
          <h2>Memes Sorted By Year Popularized</h2>
        </div>
      </div>

      <div class="row">
        <div class="col col-lg-12">
          <h3>2010</h3>
        </div>
      </div>

      <div
        class="row g-2 g-lg-3"
        v-for="meme in archiveMemes"
        v-bind:meme="meme"
        v-bind:key="meme.id"
      >
        <div class="col col-sm-12 col-md-6 col-lg-4">
          <img
            v-bind:src="meme.image"
            class="d-block w-50 img-fluid mx-auto"
            v-if="meme.show"
          />
        </div>

        <div class="col col-sm-12 col-md-6 col-lg-8">
          <h4>{{ meme.title }}</h4>
          <p>
            {{ meme.description }}
          </p>
          <p>
            Source:
            <a :href="meme.source">KnowYourMeme</a>
          </p>
          <p>
            <button v-on:click="meme.show = !meme.show">Show the Meme!</button>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ArchiveView",
  data() {
    return {
      archiveMemes: [
        {
          id: 1,
          show: true,
          image: "~/assets/images/2010/knee.jpeg",
          title: "I Took an Arrow to the Knee",
          description:
            "'I Took an Arrow in the Knee' is a memorable quote originating from the role-playing video game The Elder Scrolls V: Skyrim. An often repeated stock line throughout the game, it went on to inspire the snowclone 'I used to X, then I took an arrow to the knee'.",
          source: "https://knowyourmeme.com/memes/i-took-an-arrow-in-the-knee",
        },
        {
          id: 2,
          show: false,
          image: "~/assets/images/2010/morpheus.jpeg",
          title: "Matrix Morpheus",
          description:
            "Matrix Morpheus is an advice animal image macro series featuring a screen capture of the fictional character Morpheus (played by Lawrence Fishburne) from The Matrix franchise. The captions typically follow a two line format with the first line reading 'What if I Told You,' followed by a revelation that often belittles futile or petty behavior, in a similar vein to the advice animal characters Conspiracy Keanu and Sudden Clarity Clarence.",
          source: "https://knowyourmeme.com/memes/matrix-morpheus",
        },
        {
          id: 3,
          show: false,
          image: "~/assets/images/2010/orange.jpeg",
          title: "Annoying Orange",
          description:
            "The Annoying Orange is an american comedy web series created by Dane Boedingheimer for his own company Gagfilms in 2009 starring an anthropomorphic orange annoying other fruits, vegetables and other objects that appear in the kitchen.",
          source:
            "https://knowyourmeme.com/memes/subcultures/the-annoying-orange",
        },
      ],
    };
  },
};
</script>
