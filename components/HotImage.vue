<script>
const toggleMixin = {
  data() {
    return {
      toggled: false,
    };
  },

  methods: {
    toggledBorder() {
      this.toggled = !this.toggled;
    },
  },
};

// Create Image component for Hot Memes Page
export default {
  name: "hot-image",
  props: ["imageTitle", "imageSrc", "imageAlt", "imageDescription"],
  mixins: [toggleMixin],
};
</script>

<template>
  <div class="image card shadow-sm">
    <div class="card-body">
      <img
        :src="imageSrc"
        :alt="imageAlt"
        class="d-block w-50 img-fluid mx-auto"
        v-bind:class="{ toggled: toggled }"
      />
    </div>
    <div class="card-text">
      <div>
        <h4>{{ imageTitle }}</h4>
        <p>{{ imageDescription }}</p>
        <div class="btn-group">
          <button
            type="button"
            class="btn btn-sm btn-outline-secondary"
            @click="toggledBorder"
          >
            Click for a Surprise
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.toggled {
  border: 20px solid red;
}
</style>
