<template>
  <div class="col-sm-6 host-card">
    <div class="card">
      <div class="card-header">
        Co-Host
      </div>
      <div class="card-body">
        <h5 class="card-title">{{ name }}</h5>
        <img :src="image" :alt="`${name} profile pic`" class="host-profile">
        <p class="card-text">
          {{ bio }}
        </p>
        <a :href="`https://twitter.com/${twitter}`" class="btn btn-primary">
          <fa :icon="['fab', 'twitter']"/>
          @{{ twitter }}
        </a>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    name: {
      type: String,
    },
    bio: {
      type: String,
    },
    twitter: {
      type: String,
    },
    image: {
      type: String,
    }
  }
}
</script>
<style lang="scss" scoped>
.host-profile {
  border-radius: 100%;
  width: 25%;
}

.host-card {
  margin-bottom: 1rem;
}
</style>
