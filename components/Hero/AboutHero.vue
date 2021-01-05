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
          <button class="btn btn-outline-light">Apple Podcasts</button>
          <button class="btn btn-outline-light">Stitcher App</button>
          <button class="btn btn-outline-light">Soundcloud</button>
        </div>
    </template>
  </Hero>
</template>
<style lang="scss" scoped>
.about-subscribe {
  margin-top: 1rem;

  .btn {
    margin-bottom: 1rem;
  }
}
</style>
