<template>
  <footer>
    <p>Made with &hearts; in Austin, TX.</p>
    <p><strong>Follow us on social.</strong></p>
    <a href="https://twitter.com/cryptspeakers">
      <span class="social-icon">
        <fa :icon="['fab', 'twitter']"/>
      </span>
    </a>
  </footer>
</template>
<script>
export default {
  computed: {
    year () {
      return new Date().getFullYear()
    }
  }
}
</script>
<style lang="scss" scoped>
footer {
  background: var(--light);
  padding: 3rem;
  display: flex;
  flex-direction: column;
  justify-content: center;

  p {
    font-size: 12px;
    text-align: center;
  }

  a {
    align-self: center;
  }

  .social-icon {
    background: var(--cyan);
    border-radius: 100%;
    color: white;
    padding: 10px;
  }
}
</style>