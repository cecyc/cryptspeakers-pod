<template>
  <div class="container">
    <h2>Episode {{ id }}</h2>
  </div>
</template>
<script>
export default {
  asyncData({ params }) {
    return {
      id: params.id
    }
  }
}
</script>
