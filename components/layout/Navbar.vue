<template>
  <div class="container">
    <div class="navbar">
      <div class="navbar__left">
        <ul class="navbar__list">
          <nuxt-link tag="li" to="/" class="navbar__item">Home</nuxt-link>
          <nuxt-link
            :to="{ path: '/', hash: '#about' }"
            tag="li"
            class="navbar__item"
            >About</nuxt-link
          >
        </ul>
      </div>
      <div class="navbar__logo">
        <Logo />
      </div>
      <div class="navbar__right">
        <ul class="navbar__list">
          <nuxt-link
            tag="li"
            class="navbar__item"
            :to="{ path: '/', hash: '#portfolio' }"
            >Portfolio</nuxt-link
          >
          <nuxt-link
            tag="li"
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
import Logo from '../Logo.vue'
export default {
  name: 'Navbar',
  components: { Logo },
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
  padding: 2rem 0;
  z-index: 999;

  &__list {
    display: flex;
  }

  &__right {
    margin-right: auto;
    margin-left: 4rem;
  }

  &__left {
    margin-left: auto;
    margin-right: 4rem;
  }

  &__item {
    margin: 0 3rem;
    font-size: 2rem;
    cursor: pointer;
  }
}
</style>
