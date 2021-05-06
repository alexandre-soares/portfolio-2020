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
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {}
  },
}
</script>

<style lang="scss" scoped>
.navbar {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
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
    padding: 2rem 3rem;
  }

  &__list {
    display: flex;
  }

  &__item {
    margin: 0 3rem;
    font-size: 1.6rem;
    cursor: pointer;

    &:nth-child(1),
    &:nth-child(2),
    &:nth-child(3) {
      margin: 0 1rem;
    }

    &:last-child {
      margin-right: 0;
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
  }
  &__icon {
    width: 2rem;
    height: 2rem;
    cursor: pointer;
  }
}

.navbar.navbar--hidden {
  & .navbar__logo {
    height: 4rem;
    width: 4rem;
    transition: all 0.3s ease-in-out;
  }
}
</style>
