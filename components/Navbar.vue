<template>
  <nav class="container">
    <div class="row">
      <div class="col-sm-6 nav-title">
        <h1><a href="/" class="home-btn">CryptSpeakers</a></h1>
      </div>
      <div class="col-sm-6">
        <ul class="nav-links">
          <li><a href="/about" class="nav-link">About</a></li>
          <li><a href="/episodes" class="nav-link">Episodes</a></li>
        </ul>
      </div>
    </div>
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

.nav-title {
  text-align: center;
}

.nav-links {
  display: flex;
  justify-content: center;

  @media screen and (min-width: 600px) {
    margin: 0 0 0 2rem;
    margin-left: 2rem;
  }
}

.nav-link {
  font-size: 14px;
  font-weight: bold;
  border-bottom: 2px solid transparent;
  color: var(--indigo);
  font-family: 'Montserrat', Arial, Helvetica, sans-serif;
  margin-top: 2px;

  @media screen and (min-width: 600px) {
    font-size: 18px;
    margin-left: 2rem;
  }
}

.nav-link:hover {
  border-bottom: 2px solid var(--indigo);
}

.home-btn {
  color: black;
  text-decoration: none;
}

.home-btn:hover {
  color: var(--indigo);
}
</style>
