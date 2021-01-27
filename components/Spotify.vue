<template>
  <div>
    <iframe :src="`https://open.spotify.com/embed-podcast/episode/${episodeId}`" width="100%" height="232" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>
  </div>
</template>
<script>
export default {
  props : {
    episodeId: {
      type: String,
      required: true,
    }
  }
}
</script>