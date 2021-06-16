<template>
  <section class="projects">
    <div class="container">
      <div class="projects__wrapper">
        <div v-for="project in projects" :key="project.id" class="project" Î>
          <div class="project__card">
            <div
              class="project__img"
              :style="'background-image: url(' + project.featureImage + ')'"
            ></div>
            <div class="project__title">{{ project.name }}</div>
            <span
              class="label project__label"
              v-for="(skill, index) in project.skills"
              :key="index"
              >{{ skill }}</span
            >
            <div
              class="project__description"
              v-html="project.description"
            ></div>
            <div class="project__link">
              <button type="button">
                <a target="_blank" :href="project.link">Website</a>
              </button>
              <button type="button" v-if="project.github">
                <a target="_blank" :href="project.github">Github</a>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <span class="background-title">Projects</span>
  </section>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          id: 1,
          name: "Laura SIBILLE's Portfolio",
          skills: ['nuxtjs', 'sass'],
          link: 'https://www.laurasibille.com/',
          github: false,
          description: `
          <p>This is the website I created for the UX-UI Designer Laura SIBILLE.</p>
          `,
          featureImage: require('@/static/img/portfolio/laura-sibille-feature.png'),
          carouselImages: [
            require('@/static/img/portfolio/carousel/laura-sibille/img1.png'),
            require('@/static/img/portfolio/carousel/laura-sibille/img2.png'),
            require('@/static/img/portfolio/carousel/laura-sibille/img3.png'),
          ],
        },
        {
          id: 3,
          name: 'Netflix Movie Api',
          skills: ['vuejs', 'axios'],
          link: 'https://quirky-hugle-b33382.netlify.app',
          github:
            'https://github.com/alexandre-soares/netflix-movie-app-nuxtjs',
          description: `
          <p>A Netflix visual connected with a movie api to display a list of movies.</p>
          `,
          featureImage: require('@/static/img/portfolio/netflix-feature.png'),
          carouselImages: [
            require('@/static/img/portfolio/carousel/netflix-page/img1.png'),
            require('@/static/img/portfolio/carousel/netflix-page/img2.png'),
            require('@/static/img/portfolio/carousel/netflix-page/img3.png'),
          ],
        },
        {
          id: 5,
          name: `Requiem's Blog`,
          skills: ['vuejs', 'firebase'],
          link: 'https://joker-s-blog.web.app/',
          github: 'https://github.com/alexandre-soares/joker-blog',
          description: `
          <p>A blog where you can find some interesting articles about video games.</p>
          `,
          featureImage: require('@/static/img/portfolio/requiem-blog-featured-image.png'),
        },
        {
          id: 4,
          name: 'Music Player',
          skills: ['vuejs'],
          link: 'https://elastic-euler-fa1143.netlify.app',
          github: 'https://github.com/alexandre-soares/vuejs-music-app',
          description: `
          <p>A music player made with VueJS. Manipulation of audio files. (Desktop Only)</p>
          `,
          featureImage: require('@/static/img/portfolio/music-player-feature.png'),
          carouselImages: [
            require('@/static/img/portfolio/music-player-feature.png'),
          ],
        },
        {
          id: 6,
          name: 'Weather App',
          skills: ['vuejs'],
          description: `
          <p>An app where you can see the weather in a city.</p>
          `,
          link: 'https://flamboyant-mclean-722c14.netlify.app/',
          github: 'https://github.com/alexandre-soares/weatherapp-vuejs',
          featureImage: require('@/static/img/portfolio/weather-app-feature.png'),
        },
      ],
    }
  },
  mounted() {},
}
</script>

<style lang="scss" scoped>
.projects {
  position: relative;
  &__wrapper {
    padding: 5rem 3rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 10rem;

    @media only screen and (max-width: $bp-small) {
      grid-template-columns: 1fr;
      padding: 0 1.5rem;
    }
  }
}

.project {
  text-align: center;
  margin: 2rem 0;

  @media only screen and (max-width: $bp-small) {
    margin: 1rem 0;
  }

  &__img {
    height: 24rem;
    width: auto;
    background-size: 100%;
    background-repeat: no-repeat;
    background-position: center;
    background-color: white;
    border-radius: 0.5rem;
    overflow: hidden;
    margin: 1rem auto 2rem;
    cursor: pointer;
    position: relative;
    transition: all 0.3s ease-in;

    @media only screen and (max-width: $bp-small) {
      height: 17rem;
    }

    &:hover {
      background-size: 102%;
    }
  }

  &__title {
    font-size: 1.8rem;
  }

  &__label {
    background-color: transparent;
    border: 1px solid lightgray;
    color: black;
    margin-top: 2rem;
  }

  &__description {
    text-align: left;
    margin: 2rem 0;
  }

  &__link {
    margin-top: 4rem;
  }
}
</style>
