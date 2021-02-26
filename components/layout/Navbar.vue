<template>
  <div class="container-fluid">
    <div class="row">
      <div
        class="navbar"
        :class="!showNavbar ? 'navbar--hidden' : 'navbar--open'"
      >
        <div class="navbar__logo">
          <a href="/">
            <img
              src="@/static/img/logo/alex logo.svg"
              alt="logo"
              class="navbar__logo"
            />
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
          <a
            href="https://www.linkedin.com/in/alex-ds-soares/"
            target="_blank"
            class="navbar__item navbar__icon"
          >
            <img src="@/static/img/icon/linkedin-white.svg" alt="linkedin" />
          </a>
          <a
            href="mailto:contact@alexandresoares.fr"
            class="navbar__item navbar__icon"
          >
            <img src="@/static/img/icon/mail-white.svg" alt="linkedin" />
          </a>
          <a
            href="https://github.com/alexandre-soares"
            target="_blank"
            class="navbar__item navbar__icon"
          >
            <img src="@/static/img/icon/github-white.svg" alt="github" />
          </a>
        </ul>
        <div class="navbar__button" @click="showNavbar = !showNavbar">
          <span class="navicon"></span>
        </div>
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
      showNavbar: false,
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

  @media only screen and (max-width: $bp-small) {
    flex-direction: column;
  }

  &.navbar--hidden {
    padding: 2rem 11.5rem;

    & .navbar__item {
      font-size: 1.4rem;
    }
  }

  &__list {
    display: flex;

    @media only screen and (max-width: $bp-small) {
      flex-direction: column;
    }
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

    &:nth-child(5),
    &:nth-child(6),
    &:nth-child(7) {
      margin: 0 1rem;
    }

    &:last-child {
      margin-right: 0;
    }

    &:hover {
      background-position: 0 100%;
    }

    @media only screen and (max-width: $bp-small) {
      text-align: center;
      margin: 2rem auto;
      text-transform: uppercase;
      font-size: 1.8rem;
    }
  }

  &__logo {
    width: 5rem;
    height: 5rem;
    margin-right: auto;

    @media only screen and (max-width: $bp-small) {
      margin: auto;
    }
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

  &__icon {
    width: 2rem;
    height: 2rem;
    cursor: pointer;

    @media only screen and (max-width: $bp-small) {
      margin: 2rem auto !important;
      width: 3rem;
      height: 3rem;
      text-align: center;
    }
  }

  &__button {
    width: 5rem;
    height: 5rem;
    position: absolute;
    display: none;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    top: 1rem;
    right: 1rem;
    margin: auto;
    cursor: pointer;

    @media only screen and (max-width: $bp-small) {
      display: flex;
    }

    & .navicon {
      background: white;
      display: block;
      height: 2px;
      position: relative;
      transition: background 0.2s ease-out;
      width: 2.5rem;

      &:before,
      &:after {
        background: white;
        content: '';
        display: block;
        height: 100%;
        position: absolute;
        transition: all 0.2s ease-out;
        width: 100%;
      }

      &:before {
        top: 8px;
      }

      &:after {
        top: -8px;
      }
    }
  }
}

.navbar.navbar--hidden {
  & .navbar__logo {
    height: 6rem;
    width: 6rem;
    transition: all 0.3s ease-in-out;
  }

  & .navbar__list {
    display: none;
  }
}

.link {
  /* RESET */
  text-decoration: none;
  line-height: 1;

  position: relative;
  z-index: 0;
  display: inline-block;
  padding: 5px 5px;
  overflow: hidden;
  color: #333;
  vertical-align: bottom;
  transition: color 0.3s ease-out;
}

.link::before {
  content: '';
  position: absolute;
  z-index: -1;
  top: 0;
  left: 0;
  transform: translateY(calc(100% - 2px));
  width: 100%;
  height: 100%;
  background-image: linear-gradient(60deg, #64b3f4 0%, #c2e59c 100%);
  transition: transform 0.25s ease-out;
}

.link:hover {
  color: #fff;
}
.link:hover::before {
  transform: translateY(0);
  transition: transform 0.25s ease-out;
}

.navbar--open .navicon {
  background: transparent;
}

.navbar--open .navicon:before {
  transform: rotate(-45deg);
}

.navbar--open .navicon:after {
  transform: rotate(45deg);
}

.navbar--open:not(.steps) .navicon:before,
.navbar--open:not(.steps) .navicon:after {
  top: 0;
}
</style>
