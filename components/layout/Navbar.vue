<template>
  <div class="container-fluid">
    <div class="row">
      <div class="navbar" :class="{ 'navbar--hidden': !showNavbar }">
        <div class="navbar__logo">
          <a href="/">
            <!--<svg
              class="navbar__logo--svg"
              width="100"
              height="100"
              viewBox="0 0 452 342"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M139 330l-1-2c-2-4-2-8-1-13H29L189 31l67 121 22-16-67-121c-1-2-9-14-22-14-6 0-15 2-22 15L5 303c-1 3-8 16-2 27 4 6 10 12 24 12h136c-14 0-21-6-24-12z"
                fill="#00C58E"
              />
              <path
                d="M447 304L317 70c-2-2-9-15-22-15-6 0-15 3-22 15l-17 28v54l39-67 129 230h-49a23 23 0 0 1-2 14l-1 1c-6 11-21 12-23 12h76c3 0 17-1 24-12 3-5 5-14-2-26z"
                fill="#108775"
              />
              <path
                d="M376 330v-1l1-2c1-4 2-8 1-12l-4-12-102-178-15-27h-1l-15 27-102 178-4 12a24 24 0 0 0 2 15c4 6 10 12 24 12h190c3 0 18-1 25-12zM256 152l93 163H163l93-163z"
                fill="#2F495E"
              />
            </svg>
            -->
            <span>Alexandre SOARES</span>
          </a>
        </div>
        <ul class="navbar__list">
          <nuxt-link tag="a" to="/" class="navbar__item">Home</nuxt-link>
          <nuxt-link
            :to="{ path: '/', hash: '#about' }"
            tag="a"
            class="navbar__item"
            >About</nuxt-link
          >
          <nuxt-link
            tag="a"
            class="navbar__item"
            :to="{ path: '/', hash: '#portfolio' }"
            >Portfolio</nuxt-link
          >
          <nuxt-link
            tag="a"
            class="navbar__item"
            :to="{ path: '/', hash: '#contact' }"
            >Contact</nuxt-link
          >
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      reduceLogo: false,
      showNavbar: true,
      lastScrollPosition: 0,
    }
  },
  mounted() {
    window.addEventListener('scroll', this.onScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.onScroll)
  },
  methods: {
    onScroll() {
      const currentScrollPosition =
        window.pageYOffset || document.documentElement.scrollTop
      if (currentScrollPosition < 0) {
        return
      }
      // Stop executing this function if the difference between
      // current scroll position and last scroll position is less than some offset
      if (Math.abs(currentScrollPosition - this.lastScrollPosition) < 60) {
        return
      }
      this.showNavbar = currentScrollPosition < this.lastScrollPosition
      this.lastScrollPosition = currentScrollPosition
    },
  },
}
</script>

<style lang="scss" scoped>
.navbar {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  background-color: $primary-color;
  width: 100vw;
  padding: 2rem 11.5rem;
  z-index: 999;
  transition: all 0.3s ease-in-out;

  &.navbar--hidden {
    padding: 2rem 11.5rem;

    & .navbar__item {
      font-size: 1.4rem;
    }
  }

  &__list {
    display: flex;
  }

  &__item {
    margin: 0 3rem;
    font-size: 1.6rem;
    cursor: pointer;
    overflow: hidden;
    /* Same as before */
    background: linear-gradient(
      to right,
      rgb(156, 156, 156),
      rgb(224, 224, 224) 50%,
      rgb(243, 243, 243) 50%
    );
    /* Same as before */
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-size: 200% 100%;
    background-position: 100%;
    transition: background-position 275ms ease, font-size 0.3s ease-in-out;

    &:last-child {
      margin-right: 0;
    }

    &:hover {
      background-position: 0 100%;
    }
  }

  &__logo {
    // width: 5rem;
    // height: 5rem;
    margin-right: auto;
  }

  &__logo--svg {
    transition: all 0.3s ease-in-out;
    height: 100%;
    width: 100%;
  }

  &__logo--reduce {
    height: 1rem;
    width: 1rem;
  }
}

.navbar.navbar--hidden .navbar__logo {
  height: 4rem;
  width: 4rem;
  transition: all 0.3s ease-in-out;
}
</style>
