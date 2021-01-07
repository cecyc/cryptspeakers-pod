<template>
  <div class="container">
    <h2>Season 1</h2>
    <p>New episode every Thursday!</p>
    <Episodes :episodes="episodes" />
  </div>
</template>
<script>
import { getClient } from "~/plugins/contentful";
const contentful = getClient();

export default {
  asyncData() {
    return contentful.getEntries({
      content_type: 'episode',
      order: '-sys.createdAt',
    }).then((response) => {
      return {
        episodes: response.items.map((item) => { return item.fields })
      }
    })
  }
};
</script>
