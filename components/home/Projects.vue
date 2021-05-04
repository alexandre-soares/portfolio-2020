<template>
  <section class="projects">
    <div class="container">
      <div class="projects__wrapper">
        <div v-for="project in projects" :key="project.id" class="project" Î>
          <div class="project__card">
            <div
              class="project__img"
              :style="'background-image: url(' + project.featureImage + ')'"
            >
            </div>
            <div class="project__title">{{ project.name }}</div>
            <div class="project__description" v-html="project.description"></div>
            <div class="project__link">
              <button type="button">
                <a target="_blank" :href="project.link">Website</a>
              </button>
              <button type="button">
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
          skills: ['html', 'sass', 'javascript', 'nuxtjs'],
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
          skills: ['html', 'css', 'javascript', 'vuejs'],
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
          id: 4,
          name: 'VueJS Music Player',
          skills: ['html', 'css', 'javascript', 'vuejs'],
          link: 'https://elastic-euler-fa1143.netlify.app',
          github: 'https://github.com/alexandre-soares/vuejs-music-app',
          description: `
          <p>A music player made with VueJS. Manipulation of audio files</p>
          `,
          featureImage: require('@/static/img/portfolio/music-player-feature.png'),
          carouselImages: [
            require('@/static/img/portfolio/music-player-feature.png'),
          ],
        },
        {
          id: 5,
          name: 'VueJS Speed Writing App',
          skills: ['html', 'css', 'javascript', 'vuejs'],
          link: 'https://jovial-roentgen-b0d6a0.netlify.app',
          github: 'https://github.com/alexandre-soares/speed-writing-vuejs',
          description: `
          <p>An app where you can test your speed writing on your keyboard.</p>
          `,
          featureImage: require('@/static/img/portfolio/speed-writing-feature.png'),
          carouselImages: [
            require('@/static/img/portfolio/carousel/speed-writing/img1.png'),
            require('@/static/img/portfolio/carousel/speed-writing/img2.png'),
          ],
        },
        {
          id: 6,
          name: 'Weather App - VueJS',
          skills: ['html', 'sass', 'javascript', 'vuejs'],
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
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 3rem;

    @media only screen and (max-width: $bp-small) {
      height: auto;
      padding: 0 1.5rem;
    }
  }
}

.project {
  text-align: center;
  margin: 2rem 0;

  &__img {
    height: 17rem;
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
      height: 25rem;
    }

    &:hover {
      background-size: 102%;
    }
  }


  &__title {
    font-size: 1.8rem;
  }

  &__description {
    text-align: left;
    margin: 2rem 0;
  }

  &__link {
    margin-top: 4rem;
  }
}

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
  transition: color .7s ease-in;
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

/* The Modal (background) */
.modal {
  display: none; /* Hidden by default */
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgb(0, 0, 0); /* Fallback color */
  background-color: rgba(0, 0, 0, 0.4); /* Black w/ opacity */
}

/* Modal Content/Box */
.modal-content {
  background-color: #fefefe;
  margin: 15% auto; /* 15% from the top and centered */
  padding: 20px;
  border: 1px solid #888;
  width: 80%; /* Could be more or less, depending on screen size */
}

/* The Close Button */
.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}
</style>
