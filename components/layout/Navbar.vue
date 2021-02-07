<template>
  <div class="container">
    <div class="navbar">
      <div class="navbar__left">
        <ul class="navbar__list">
          <li class="navbar__item">Home</li>
          <li class="navbar__item">About</li>
        </ul>
      </div>
      <div class="navbar__logo">
        <Logo />
      </div>
      <div class="navbar__right">
        <ul class="navbar__list">
          <li class="navbar__item">Portfolio</li>
          <li class="navbar__item">Contact</li>
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
  padding: 2rem 0;

  &__list {
    display: flex;
  }

  &__item {
    margin: 0 3rem;
    font-size: 2rem;
  }
}
</style>
