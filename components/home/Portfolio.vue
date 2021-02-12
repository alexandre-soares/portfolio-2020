<template>
  <div class="portfolio">
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <h2 class="portfolio__title">Portfolio</h2>
        </div>
      </div>
      <div class="row">
        <nuxt-link
          v-for="project in projects"
          :key="project.id"
          :to="'/portfolio/' + project.id"
          target="_blank"
          class="col-4"
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
          name: "Laura SIBILLE's Portfolio",
          featureImage: require('@/static/img/portfolio/laura-sibille/feature-image.png'),
        },
        {
          id: 2,
          name: 'Color Steps',
          featureImage:
            'https://d33wubrfki0l68.cloudfront.net/6019aa270b38eb000785d37c/screenshot.png',
        },
        {
          id: 3,
          name: 'Netflix Movie Api',
          featureImage:
            'https://d33wubrfki0l68.cloudfront.net/6019a986b355d60121acbf5f/screenshot.png',
        },
        {
          id: 4,
          name: 'VueJS Music Player',
          featureImage:
            'https://d33wubrfki0l68.cloudfront.net/6019accc4759ba0008e6c6c6/screenshot.png',
        },
        {
          id: 5,
          name: 'VueJS Speed Writing App',
          featureImage:
            'https://d33wubrfki0l68.cloudfront.net/6019aac81824b200074d8e16/screenshot.png',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.portfolio {
  height: 100vh;
  padding: 0 10rem;
  display: flex;
  align-items: center;
  justify-content: center;

  &__title {
    font-size: 5rem;
    font-weight: 200;
    margin: 2rem 0 5rem;
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
    height: 100%;
    width: 100%;
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
