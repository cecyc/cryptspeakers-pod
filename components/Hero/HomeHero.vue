<template>
    <Hero>
      <template v-slot:left>
        <img :src="heroImg" alt="CryptSpeakers logo" class="hero-img" />
      </template>
      <template v-slot:right>
          <h2>Hello Boyles and Ghouls!</h2>
          <p>Welcome to CryptSpeakers, a Tales from the Crypt podcast!</p>
          <p>
            Join hosts Jay Tyler and Cecy Correa every week for a new episode of
            Tales from the Crypt. Will it be a Keeper or a Stinker? Only one way
            to find out. Listen and subscribe below!
          </p>
          <div v-if="providers" class="hero-subscribe">
            <a v-for="(provider, id) in providers" 
              :key="id" 
              :href="provider.subscriptionUrl"
              class="btn btn-outline-light ep-btn">
                Subscribe on {{ provider.name }}
            </a>
          </div>
      </template>
    </Hero>
</template>
<script>
import CryptSpeakersHero from "~/assets/images/cryptspeakers-hero.jpg";
import { getClient } from "~/plugins/contentful";
const contentful = getClient();

export default {
  data() {
    return {
      heroImg: CryptSpeakersHero,
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
