<template>
  <footer>
    <div class="container">
      <div class="row">

        <div class="col-sm-6">
          <h4>Listen on</h4>
          <ul class="footer-listen">
            <li><a href="">Apple Podcasts</a></li>
            <li><a href="">Spotify</a></li>
            <li><a href="">Stitcher</a></li>
          </ul>
        </div>

        <div class="col-sm-6">
          <h4>Follow us</h4>
          <a href="https://twitter.com/cryptspeakers">
            <span class="social-icon">
              <fa :icon="['fab', 'twitter']" />
            </span>
          </a>
        </div>

      </div>
    </div>
  </footer>
</template>
<script>
export default {
  computed: {
    year() {
      return new Date().getFullYear();
    }
  }
};
</script>
<style lang="scss" scoped>
h4 {
  border-bottom: 2px solid black;
  font-family: 'Oswald', Arial, Helvetica, sans-serif;
  margin: 2rem 0;
}

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

  .footer-listen {
    list-style-type: none;
    display: flex;
    margin: 0;
    padding: 0;

    li {
      margin-right: 2rem;
    }
  }
}
</style>
