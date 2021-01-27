<template>
  <footer>
    <div class="container">
      <div class="row">
        <div v-if="providers" class="col-sm-6">
          <h4>Listen on</h4>
          <ul class="footer-listen">
            <li v-for="(provider, id) in providers" :key="id">
              <a :href="provider.subscriptionUrl">{{ provider.name }}</a>
            </li>
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
import { getClient } from "~/plugins/contentful";
const contentful = getClient();

export default {
  data() {
    return {
      providers: []
    };
  },
  computed: {
    year() {
      return new Date().getFullYear();
    }
  },
  methods: {
    fetchProviders() {
      contentful
        .getEntries({
          content_type: "metaData"
        })
        .then(response => {
          const data = response.items[0].fields.providers;
          this.providers = data.map(item => {
            return item.fields;
          });
        });
    }
  },
  mounted() {
    this.fetchProviders();
  }
};
</script>
<style lang="scss" scoped>
h4 {
  border-bottom: 2px solid black;
  font-family: "Oswald", Arial, Helvetica, sans-serif;
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
