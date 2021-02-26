<template>
  <div id="portfolio" class="featured-projects">
    <div class="container">
      <div class="row align-items-center section-title">
        <span class="title-line"></span>
        <h2>Featured Projects</h2>
      </div>
      <div class="row">
        <div class="col-12">
          <div v-for="project in projects" :key="project.id" class="project">
            <div class="row">
              <div class="col-lg-6 project__infos">
                <h4 class="project__title">{{ project.name }}</h4>
                <p class="project__paragraph" v-html="project.description"></p>
                <div class="project__labels">
                  <div
                    v-for="(skill, index) in project.skills"
                    :key="index"
                    class="project__label label"
                  >
                    {{ skill }}
                  </div>
                </div>
                <div class="project__links">
                  <a target="_blank" :href="project.link">View the project</a>
                  <a target="_blank" :href="project.github">Github</a>
                </div>
              </div>
              <div class="col-lg-6">
                <VueSlickCarousel :arrows="true" v-bind="settings">
                  <img
                    v-for="(img, index) in project.carouselImages"
                    :key="index"
                    :src="img"
                    alt="img"
                    class="project__img"
                  />
                </VueSlickCarousel>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
// optional style for arrows & dots
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
export default {
  components: { VueSlickCarousel },
  data() {
    return {
      settings: {
        dots: true,
        dotsClass: 'slick-dots custom-dot-class',
        edgeFriction: 0.35,
        infinite: true,
        speed: 500,
        slidesToShow: 1,
        slidesToScroll: 1,
        prevArrow: false,
        nextArrow: false,
      },
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
          id: 2,
          name: 'Color Steps',
          skills: ['html', 'css', 'javascript', 'vuejs'],
          link: 'https://musing-edison-888771.netlify.app/',
          github: 'https://github.com/alexandre-soares/color-steps-vuejs',
          description: `
          <p>A little application where you find colors between 2 selected colors.</p>
          `,
          featureImage: require('@/static/img/portfolio/color-step-feature.png'),
          carouselImages: [
            require('@/static/img/portfolio/carousel/color-steps/img1.png'),
            require('@/static/img/portfolio/carousel/color-steps/img2.png'),
            require('@/static/img/portfolio/carousel/color-steps/img3.png'),
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
          <p>A Netflix visual connected with a movie api to display a list of movies. The front page is just HTML and CSS. After clicking on the "watch" button, there is an api request with Axios to fetch movies from the movie database (TMDb).</p>
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
          <p>A music player made with VueJS.</p>
          <p>Use and manipulation of audio files</p>
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
          <p>An app where you can test your accuracy and speed writing while pressing inputs on your keyboard.</p>
          `,
          featureImage: require('@/static/img/portfolio/speed-writing-feature.png'),
          carouselImages: [
            require('@/static/img/portfolio/carousel/speed-writing/img1.png'),
            require('@/static/img/portfolio/carousel/speed-writing/img2.png'),
          ],
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.featured-projects {
  z-index: 999;
}

.project {
  margin: 20rem 0;

  @media only screen and (max-width: $bp-small) {
    margin: 3rem 0 10rem;
  }

  &__infos {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  &__title {
    font-size: 2.6rem;

    @media only screen and (max-width: $bp-small) {
      text-align: center;
      margin: 2rem 0;
    }
  }

  &__img {
    border-radius: 1.5rem;
    overflow: hidden;
  }

  &__paragraph {
    font-size: 1.4rem;
    line-height: 1.4;
    width: 85%;
    text-align: justify;
    @media only screen and (max-width: $bp-small) {
      width: 90%;
    }
  }

  &__links {
    & a {
      padding: 1rem 2rem;
      margin-right: 2rem;
      font-size: 1.6rem;
      border-bottom: 1px solid $light-red;

      @media only screen and (max-width: $bp-small) {
        margin: 3rem;
        display: block;
        text-align: center;
        width: 90%;
      }
    }
  }
}
</style>
