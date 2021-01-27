<template>
  <section class="hero-wrapper hero-background">
    <div class="container">
      <div class="row">
        <div class="col-sm-6 no-left-padding">
          <slot name="left"></slot>
        </div>

        <div class="col-sm-6 hero-text">
          <slot name="right"></slot>
        </div>
      </div>
    </div>
  </section>
</template>
<style lang="scss" scoped>
.hero-wrapper {
  img {
    width: 100%;
    max-width: 400px;
    margin-bottom: 1rem;
  }

  .hero-text {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    padding-left: 0;

    @media screen and (min-width: 600px) {
      padding-left: 15px;
    }

    .hero-subscribe {
      margin-top: 1rem;
    }
  }
}

.hero-background {
  color: white;
  background: var(--indigo);
  padding: 2rem;

  @media screen and (min-width: 600px) {
    padding: 2rem 0;
  }
}

.ep-btn {
   margin-right: 1rem;
   margin-bottom: 1rem;
 }
</style>
