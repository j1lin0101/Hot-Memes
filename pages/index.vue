<script>
import Navbar from "../components/Navbar.vue";

export default {
  name: "IndexPage",
  components: {
    Navbar,
  },
  head() {
    return {
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Welcome to the Hottest Meme Website on the Internetn",
        },
      ],
    };
  },
};
</script>


<template>
  <div>
    <div class="container py-4">
      <navbar></navbar>
      <!-- Create Jumbotron -->
      <div class="p-5 mb-4 bg-light rounded-3">
        <div class="container-fluid py-5">
          <div class="jumbo-img"></div>
          <h1 class="display-5 fw-bold">Welcome to the Hot Meme Network</h1>
          <p class="col-md-8 fs-4">
            Find the latest and greatest in meme culture.
          </p>
        </div>
      </div>

      <!-- Two Text Areas with Buttons -->
      <div class="row align-items-md-stretch">
        <div class="col-md-6">
          <div class="h-100 p-5 border rounded-3 bg-light">
            <h2>View the Hottest Memes of the Week</h2>
            <p>See what the kids are raving about these days</p>
            <!-- Tooltip Description on Hover -->
            <a href="hot.html"
              ><button
                type="button"
                class="btn btn-primary"
                data-toggle="tooltip"
                data-placement="top"
                title="See the hottest memes of the week"
              >
                Hot Memes
              </button></a
            >
          </div>
        </div>
        <div class="col-md-6">
          <div class="h-100 p-5 border rounded-3 bg-light">
            <h2>Catch Up on Meme Culture</h2>
            <p>
              See what memes were popular in the past year to understand meme
              templates and other Gen Z humor tidbits
            </p>
            <!-- Tooltip Description on Hover -->
            <a href="archive.html"
              ><button
                type="button"
                class="btn btn-primary"
                data-toggle="tooltip"
                data-placement="top"
                title="Take a journey through meme history"
              >
                Meme Archive
              </button></a
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

