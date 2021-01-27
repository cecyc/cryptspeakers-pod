<template>
  <Hero>
    <template v-slot:left>
      <h2>About the podcast</h2>
      <p><strong>CryptSpeakers</strong> is a Tales from the Crypt podcast, where hosts Jay Tyler and Cecy Correa discuss a different epsisode from the classic 90s series, one by one, in chronological order.</p>
      <p>The pod attempts to bring a little of historical context to each episode by discussing the background of those involved in the making of the episode. We also do a bit of modern-day fancasting, and offer recommendations relevant to each episode.</p>
      <p><strong>Legal stuff:</strong> We are in no way affiliated with Tales from the Crypt, we are just fans who want to discuss the legacy the show has had on the horror genre.</p>
    </template>
    <template v-slot:right>
      <h3>Listen on</h3>
        <div class="about-subscribe">
          <a
            v-for="(provider, id) in providers"
            :key="id"
            :href="provider.subscriptionUrl"
            class="btn btn-outline-light ep-btn">
              {{ provider.name }}
          </a>
        </div>
    </template>
  </Hero>
</template>
<script>
import { getClient } from "~/plugins/contentful";
const contentful = getClient();

export default {
  data() {
    return {
      providers: [],
    }
  },
  methods: {
    fetchProviders() {
      contentful
        .getEntries({
          content_type: "metaData"
        })
        .then(response => {
          const data = response.items[0].fields.providers;
          this.providers = data.map(item => {
            return item.fields;
          });
        });
    }
  },
  mounted() {
    this.fetchProviders();
  }
}
</script>
<style lang="scss" scoped>
.about-subscribe {
  margin-top: 1rem;

  .btn {
    margin-bottom: 1rem;
  }
}
</style>
