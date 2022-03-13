<script>
export default {
  name: "archive-meme",
  props: ["memeTitle", "memeSrc", "memeDesc", "memeSource", "show"],
};
</script>


<template>
  <div class="row">
    <div class="col col-sm-12 col-md-6 col-lg-4">
      <img :src="memeSrc" class="d-block w-50 img-fluid mx-auto" v-if="show" />
    </div>

    <div class="col col-sm-12 col-md-6 col-lg-8">
      <h4>{{ memeTitle }}</h4>
      <p>
        {{ memeDesc }}
      </p>
      <p>
        Source:
        <a :href="memeSource">KnowYourMeme</a>
      </p>
      <p>
        <button v-on:click="show = !show">Show the Meme!</button>
      </p>
    </div>
  </div>
</template>