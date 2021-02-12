<template>
  <div class="project">
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <h1 class="project__title">
            {{ projects[this.$route.params.id - 1].name }}
          </h1>
          <div v-html="projects[this.$route.params.id - 1].description"></div>
          <h2>Languages - Frameworks</h2>
          <div class="label__wrapper">
            <span
              v-for="(skill, index) in projects[this.$route.params.id - 1]
                .skills"
              :key="index"
              class="label"
              :class="'label--' + skill"
            >
              {{ skill }}
            </span>
          </div>
          <h2>Links</h2>
          <div class="links__wrapper">
            <a
              :href="projects[this.$route.params.id - 1].link"
              target="_blank"
              class="btn"
              >Go to the website</a
            >
            <a
              v-if="projects[this.$route.params.id - 1].github"
              :href="projects[this.$route.params.id - 1].github"
              target="_blank"
              ><img
                src="@/static/img/icon/github-white.svg"
                alt="github"
                class="icon"
            /></a>
          </div>
        </div>
        <div class="col">
          <img
            :src="projects[this.$route.params.id - 1].featureImage"
            alt="img"
            class="project__img"
          />
        </div>
      </div>
    </div>
  </div>
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
          featureImage: require('@/static/img/portfolio/laura-sibille/feature-image.png'),
          carouselImages: [],
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
          featureImage:
            'https://d33wubrfki0l68.cloudfront.net/6019aa270b38eb000785d37c/screenshot.png',
          carouselImages: [],
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
          featureImage:
            'https://d33wubrfki0l68.cloudfront.net/6019a986b355d60121acbf5f/screenshot.png',
          carouselImages: [],
        },

        {
          id: 4,
          name: 'VueJS Music Player',
          skills: ['html', 'css', 'javascript', 'vuejs'],
          link: 'https://elastic-euler-fa1143.netlify.app',
          github: 'https://github.com/alexandre-soares/vuejs-music-app',
          description: `
          <p>A music player made with VueJS.</p>
          `,
          featureImage:
            'https://d33wubrfki0l68.cloudfront.net/6019accc4759ba0008e6c6c6/screenshot.png',
          carouselImages: [],
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
          featureImage:
            'https://d33wubrfki0l68.cloudfront.net/6019aac81824b200074d8e16/screenshot.png',
          carouselImages: [],
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.project {
  height: 70vh;
  padding: 0 10rem;
  display: flex;
  align-items: center;
  justify-content: center;

  &__title {
    font-size: 5rem;
    font-weight: 200;
    margin: 2rem 0 5rem;
    letter-spacing: 2px;
  }

  & h2 {
    font-size: 3rem;
    font-weight: 400;
    letter-spacing: 2px;
  }

  & ::v-deep p {
    line-height: 1.6;
    font-size: 2rem;
    margin: 2rem 0 4rem;
    text-align: justify;
  }
}

.label {
  &__wrapper {
    text-align: left;
    margin: 3rem 0;
  }
}

.links {
  &__wrapper {
    display: flex;
    align-items: center;
    justify-content: flex-start;

    & a {
      margin: 2rem;
    }
  }
}
</style>
