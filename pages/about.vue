<template>
  <div>
    <AboutHero />
    <div class="container hosts-wrapper">
      <div class="row">
        <Host
          v-for="(host, idx) in hostData"
          :key="idx"
          :name="host.name"
          :image="host.image.fields.file.url"
          :bio="host.bio"
          :twitter="host.twitter"
        />
      </div>
    </div>
  </div>
</template>
<script>
import { getClient } from '~/plugins/contentful'
const contentful = getClient()

export default {
  asyncData () {
    return contentful.getEntries({
      content_type: 'host'
    }).then((response) => {
      return {
        hostData: response.items.map((item) => { return item.fields })
      }
    })
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
