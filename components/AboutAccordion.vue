<script>
export default {
  name: "about-accordion",
  props: ["accordionTitle", "accordionDescription", "accordionId"],
};
</script>

<template>
  <div>
    <div class="mb-3">
      <b-button v-b-toggle="'my-collapse' + accordionId">{{
        accordionTitle
      }}</b-button>
    </div>

    <b-collapse :id="'my-collapse' + accordionId">
      <b-card :title="accordionTitle">{{ accordionDescription }}</b-card>
    </b-collapse>
  </div>
</template>
