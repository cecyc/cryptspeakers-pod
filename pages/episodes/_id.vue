<template>
  <div class="container">
    <h2>{{ episode.title }}</h2>
    <span class="badge episode-num">{{ episode.episodeNumber }}</span>
    <div class="row">
      <div v-if="episode" class="col-sm-6">
        <div class="episode-image">
          <img :src="imageUrl" :alt="`Episode ${episode.title} cover art`">
        </div>
      </div>
      <div class="col-sm-6">
        <h3>Episode Details</h3>
        <p><strong>Director:</strong> {{ episode.director }}</p>
        <p><strong>Writer:</strong> {{ episode.writer }}</p>
        <p><strong>Starring:</strong> {{ episode.starring }}</p>
      </div>
    </div>
    <div class="row">
      <div class="col-lg-6">
        <p>{{ episode.description }}</p>
      </div>
    </div>
    <div v-if="episode.spotifyId" class="row">
      <div class="col-lg-6">
        <h3>Listen!</h3>
        <Spotify :episodeId="episode.spotifyId" />
      </div>
    </div>
  </div>
</template>
<script>
import { getClient } from '~/plugins/contentful.js'
const contentful = getClient()

export default {
  asyncData({ params }) {
    return contentful.getEntries({
      content_type: 'episode',
      'fields.episodeUrl': params.id,
    }).then(response => {
      return {
        episode: response.items[0].fields
      }
    })
  },
  computed: {
    imageUrl () {
      return this.episode.coverArt.fields.file.url
    }
  }
}
</script>
<style lang="scss" scoped>
.episode-num {
  margin-bottom: 1rem;
}

.episode-image {
  margin-bottom: 1rem;
  img {
    width: 100%;
    max-width: 450px;
  }
}
</style>