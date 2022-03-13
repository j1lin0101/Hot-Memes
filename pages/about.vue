<script>
import AboutAccordion from "../components/AboutAccordion.vue";

export default {
  components: {
    AboutAccordion,
  },
  data() {
    return {
      aboutDetails: [
        {
          id: 1,
          title: "Who We Are",
          content:
            "The Hot Meme Network is run by a guy with way too much time on his hands who also spends way too much time on his phone. This knowledge that he has could be used to serve the greater world and its problems. Instead he wastes his time on memes on Reddit.",
        },
        {
          id: 2,
          title: "Why Hot Memes",
          content:
            "One day I found a particular meme very histerical. Wanting this to be a moment to connect with my mother, I shared it with her. Instead of laughing, she gave me a very concerned and sympathetic look. 'How do you find this funny?' It occurred to me at that moment that our senses of humor were out of sync. I wanted to give her a breakdown of why it was funny, but it occurred to me that meme history is so deep and lore-filled for no apparently good reason. The Hot Meme Network functions as that bridge between history and now. Giving an abridged version of internet culture with the intent of catching people up and bringing the culture gap closer.",
        },
        {
          id: 3,
          title: "How can I support?",
          content: "Buy me a coffee! Venmo at jlin0104",
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
    <h1>About Us</h1>

    <!-- Accordion with Descriptions -->
    <div>
      <about-accordion
        v-for="detail in aboutDetails"
        v-bind:detaill="detail"
        v-bind:key="detail.id"
        v-bind:accordionId="detail.id"
        v-bind:accordionTitle="detail.title"
        v-bind:accordionDescription="detail.content"
      ></about-accordion>
    </div>
  </div>
</template>

