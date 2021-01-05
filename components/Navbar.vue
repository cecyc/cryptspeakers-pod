<template>
  <nav class="container">
    <h1>CryptSpeakers</h1>
    <ul class="nav__links">
      <li><a href="/about" class="nav__link">About</a></li>
      <li><a href="/episodes" class="nav__link">Episodes</a></li>
    </ul>
  </nav>
</template>
<style lang="scss" scoped>
nav {
  display: flex;
  align-content: center;
  align-items: center;
  padding: 1rem 0;

  h1 {
    margin-bottom: 0;
  }
}

nav ul {
  list-style-type: none;
  padding: 0 !important;
}

.nav__links {
  margin: 0 0 0 2rem;
  margin-left: 2rem;
  display: flex;
}

.nav__link {
  margin-left: 2rem;
  color: var(--indigo);
}
</style>
