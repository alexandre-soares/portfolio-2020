<template>
  <div class="other-projects">
    <div class="container">
      <div class="row align-items-center section-title">
        <span class="title-line"></span>
        <h2>Other Projects</h2>
      </div>
      <div class="row align-items-center justify-content-start">
        <div
          v-for="project in projects"
          :key="project.id"
          class="project col-sm-12 col-lg-4"
        >
          <div class="project__card">
            <div
              class="project__img"
              :style="'background-image: url(' + project.featureImage + ')'"
            >
              <div class="project__check"><span>Website</span></div>
            </div>
            <div class="project__title">{{ project.name }}</div>
            <div class="project__link">
              <button type="button">
                  <a target="_blank" :href="project.github">Github</a>
              </button>
            </div>
        
          </div>
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
          name: 'Weather App - VueJS',
          skills: ['html', 'sass', 'javascript', 'vuejs'],
          link: 'https://flamboyant-mclean-722c14.netlify.app/',
          github: 'https://github.com/alexandre-soares/weatherapp-vuejs',
          featureImage: require('@/static/img/portfolio/weather-app-feature.png'),
        },
        {
          id: 2,
          name: 'Trello Clone - VueJS',
          skills: ['html', 'sass', 'javascript', 'vuejs'],
          link: 'https://trusting-neumann-3ca456.netlify.app/',
          github: 'https://github.com/alexandre-soares/trello-clone',
          featureImage: require('@/static/img/portfolio/trello-clone-feature.png'),
        },
        {
          id: 3,
          name: 'Beatmaker Javascript',
          skills: ['html', 'sass', 'javascript'],
          link: 'https://unruffled-poitras-e30bcb.netlify.app/',
          github:
            'https://github.com/alexandre-soares/beatmaker-vanillajshttps://github.com/alexandre-soares/beatmaker-vanillajs',
          featureImage: require('@/static/img/portfolio/beatmaker-js-feature.png'),
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.other-projects {
  background-color: black;
  padding: 5rem 0;
}

.project {
  text-align: center;
  margin: 2rem 0;
  &__card {
  }

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

      & .project__check {
        display: flex;
      }
    }
  }

  &__check {
    position: absolute;
    top: 0;
    left: 0;
    display: none;
    justify-content: center;
    align-items: center;
    font-size: 1.7rem;

    height: 100%;
    width: 100%;
    background-color: rgba(63, 63, 63, 0.37);
  }

  &__title {
    font-size: 1.8rem;
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
