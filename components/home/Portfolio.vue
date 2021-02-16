<template>
  <div id="portfolio" class="portfolio">
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <h2>Portfolio</h2>
        </div>
      </div>
      <div class="row">
        <nuxt-link
          v-for="project in projects"
          :key="project.id"
          tag="a"
          :to="'/portfolio/' + project.id"
          class="col-sm-12 col-lg-4"
        >
          <div class="card">
            <div class="card__img">
              <img :src="project.featureImage" alt="img" />
            </div>
            <div class="card__title">
              <h3>{{ project.name }}<span class="card__title--end">_</span></h3>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Portfolio',
  data() {
    return {
      projects: [
        {
          id: 1,
          name: "NuxtJS - Laura SIBILLE's Portfolio",
          featureImage: require('@/static/img/portfolio/laura-sibille-feature.png'),
        },
        {
          id: 2,
          name: 'VueJS - Color Steps',
          featureImage: require('@/static/img/portfolio/color-step-feature.png'),
        },
        {
          id: 3,
          name: 'NuxtJS - Netflix Movie Api',
          featureImage: require('@/static/img/portfolio/netflix-feature.png'),
        },
        {
          id: 4,
          name: 'VueJS - Music Player',
          featureImage: require('@/static/img/portfolio/music-player-feature.png'),
        },
        {
          id: 5,
          name: 'VueJS - Speed Writing App',
          featureImage: require('@/static/img/portfolio/speed-writing-feature.png'),
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.portfolio {
  //height: 100vh;
  padding: 0 10rem;
  display: flex;
  align-items: center;
  justify-content: center;

  @media only screen and (max-width: $bp-small) {
    height: auto;
    padding: 0 1.5rem;
  }
}

.card {
  position: relative;
  cursor: pointer;
  transition: 0.3s ease-in;
  margin: 3rem 0;

  &:hover {
    & .card__img {
      filter: grayscale(0);
    }
    & .card__title {
      opacity: 1;
    }

    & .card__title--end {
      animation: endSpan 0.2s infinite alternate;
    }
  }

  &__img {
    filter: grayscale(1);
  }

  &__title {
    background-color: rgba(43, 43, 43, 0.801);
    height: 100.5%;
    width: 100.5%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    transition: 0.2s ease-in;

    & h3 {
      font-size: 3rem;
      letter-spacing: 5px;
      font-weight: 200;
      text-align: center;
      width: 80%;
    }

    &--end {
      opacity: 0;
    }
  }
}

@keyframes endSpan {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }
}
</style>
