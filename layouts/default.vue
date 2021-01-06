<template>
  <div>
    <Navbar />
    <Nuxt />
    <Footer />
  </div>
</template>

<style>
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.no-left-padding {
  padding-left: 0;
}

.episode-num {
  background: var(--indigo);
  color: white;
  margin: 1rem 0;
}

h1, h2 {
  font-family: 'Oswald', Arial, Helvetica, sans-serif;
  text-transform: uppercase;
}

p, button {
  font-family: 'Montserrat', Arial, Helvetica, sans-serif;
}
</style>
