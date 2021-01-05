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
          <div v-if="latestEpisode" class="latest-episode">
            <h3>Latest episode</h3>
            <iframe
              width="100%"
              height="166"
              scrolling="no"
              frameborder="no"
              allow="autoplay"
              :src="
                `https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/${ep.trackId}&color=%23ff5500&auto_play=false&hide_related=false&show_comments=false&show_artwork=false&show_user=false`
              "
            ></iframe>
          </div>
          <div class="hero-subscribe">
            <button class="btn btn-outline-light">Subscribe</button>
          </div>
      </template>
    </Hero>
</template>
<script>
import CryptSpeakersHero from "~/assets/images/cryptspeakers-hero.jpg";

export default {
  data() {
    return {
      heroImg: CryptSpeakersHero,
      latestEpisode: false,
    }
  }
}
</script>
