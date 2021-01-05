<template>
  <div>
    <AboutHero />
    <div class="container hosts-wrapper">
      <div class="row">
        <Host
          v-for="(host, idx) in hostData"
          :key="idx"
          :name="host.name"
          :image="host.image"
          :bio="host.bio"
          :twitter="host.twitter"
        />
      </div>
    </div>
  </div>
</template>
<script>
import hosts from "~/static/hosts.js";

export default {
  data() {
    return {
      hostData: hosts
    };
  }
};
</script>
<style lang="scss" scoped>
.hosts-wrapper {
  padding: 2rem;

  @media screen and (min-width: 600px) {
    padding: 2rem 0;
  }
}
</style>
