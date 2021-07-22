<template>
  <section class="projects">
    <h2 class="mobile-title">Projects</h2>
    <div class="container">
      <div class="projects__wrapper">
        <div v-for="project in projects" :key="project.id" class="project" Î>
          <div class="project__card">
            <a target="_blank" :href="project.link">
              <img :src="project.featureImage" alt="img" class="project__img" />
            </a>
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
        },
        {
          id: 7,
          name: 'Invoice App',
          skills: ['vuejs', 'vuex', 'firebase'],
          description: `
          <p>An Invoice app with realtime update.</p>
          `,
          link: 'https://vuejs-invoice-app.web.app/',
          github: 'https://github.com/alexandre-soares/vuejs-invoice-app',
          featureImage: require('@/static/img/portfolio/invoice-app-feature.png'),
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
        },
        {
          id: 5,
          name: `Requiem's Blog`,
          skills: ['vuejs', 'firebase', 'crud'],
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
          skills: ['vuejs', 'firebase', 'crud'],
          description: `
          <p>An app where you can check the weather.</p>
          `,
          link: 'https://vuejs-weather-app-7dab4.web.app/',
          github: 'https://github.com/alexandre-soares/vuejs-weather-app',
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
    grid-gap: 3rem;

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
    height: 100%;
    width: 100%;
    border-radius: 0.5rem;
    overflow: hidden;
    margin: 1rem auto 2rem;
    cursor: pointer;
    position: relative;
    transition: all 0.3s ease-in;
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

// Buttons

button {
  margin: 0 2rem;
  font-size: 1.6rem;
  font-family: 'Hind Guntur', sans-serif;
  line-height: 1;
  letter-spacing: 0.025em;
  padding: 1.1rem;
  cursor: pointer;
  color: white;
  border: 0;
  border-bottom: 1px solid $light-red;
  border-radius: 2px;
  min-width: 12rem;
  overflow: hidden;
  position: relative;
  background-color: transparent;
}

button a {
  display: block;
  position: relative;
  z-index: 10;
  transition: color 0.7s ease-in;
}

button:after,
button:before {
  padding: 1.1rem 0;
  content: '';
  position: absolute;
  top: 0;
  left: calc(-100% - 30px);
  height: 100%;
  width: calc(100% + 20px);
  color: #fff;
  border-radius: 2px;
  transform: skew(-25deg);
}

button:after {
  background: #fff;
  transition: left 0.8s cubic-bezier(0.86, 0, 0.07, 1) 0.2s;
  z-index: 0;
  opacity: 0.8;
}

button:before {
  background: $light-red;
  z-index: 5;
  transition: left 1s cubic-bezier(0.86, 0, 0.07, 1);
}

button:hover a {
  color: white !important;
}

button:hover:after {
  left: calc(0% - 10px);
  transition: left 0.8s cubic-bezier(0.86, 0, 0.07, 1);
}

button:hover:before {
  left: calc(0% - 10px);
  transition: left 1s cubic-bezier(0.86, 0, 0.07, 1);
}
</style>
