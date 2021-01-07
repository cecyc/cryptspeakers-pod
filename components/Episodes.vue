<template>
  <section class="episodes-wrapper container">
    <div v-if="episodes" class="row row-cols-1 row-cols-md-3 g-4">

      <div v-for="(ep, idx) in episodes" :key="idx" class="col episode">
        <div class="card">
          <img :src="ep.coverArt.fields.file.url" class="card-img-top" aria-hidden="true" />
          <div class="card-body">
            <h5 class="card-title">{{ ep.title }}</h5>
            <span class="badge episode-num">{{ ep.episodeNumber }}</span>
            <p class="card-text">{{ ep.description }}</p>
            <button class="btn btn-outline-dark">Listen</button>
          </div>
        </div>
      </div>

    </div>
    <div v-else>
      <p>New episodes coming soon!</p>
    </div>
  </section>
</template>
<script>
export default {
  props: {
    episodes: {
      type: Array,
      required: true,
    }
  }
}
</script>
<style lang="scss" scoped>
.episodes-wrapper {
  padding: 2rem;

  @media screen and (min-width: 600px) {
    padding: 2rem 0;
  }

  .episode {
    margin-bottom: 1rem;
  }

  .card-title {
    margin-bottom: -0.25rem;
  }
}
</style>
