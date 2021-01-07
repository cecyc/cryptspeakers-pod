<template>
  <div>
    <HomeHero />
    <Episodes :episodes="episodes" />
  </div>
</template>
<script>
import { getClient } from "~/plugins/contentful";
const contentful = getClient();

export default {
  asyncData () {
    return contentful.getEntries({
      content_type: 'episode',
      order: '-sys.createdAt',
      limit: 3,
    }).then((response) => {
      return {
        episodes: response.items.map((item) => { return item.fields })
      }
    })
  }
};
</script>
