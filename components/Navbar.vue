<template>
  <nav class="container">
    <h1>CryptSpeakers</h1>
    <ul class="nav-links">
      <li><a href="/about" class="nav-link">About</a></li>
      <li><a href="/episodes" class="nav-link">Episodes</a></li>
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

.nav-links {
  margin: 0 0 0 2rem;
  margin-left: 2rem;
  display: flex;
}

.nav-link {
  border-bottom: 2px solid transparent;
  color: var(--indigo);
  font-family: 'Montserrat', Arial, Helvetica, sans-serif;
  font-size: 18px;
  font-weight: bold;
  margin-left: 2rem;
  margin-top: 2px;
}

.nav-link:hover {
  border-bottom: 2px solid var(--indigo);
}
</style>
