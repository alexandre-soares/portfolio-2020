<template>
  <div>
    <Navbar />
    <Nuxt />
  </div>
</template>

<script>
import Navbar from '@/components/layout/Navbar.vue'
export default {
  components: {
    Navbar,
  },
}
</script>

<style lang="scss">
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  font-size: 62.5%;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background-color: $primary-color;
  color: $secondary-color;
}

ul {
  list-style: none;
}

h1,
h2,
h3,
h4 {
  color: $secondary-color;
}

a {
  color: $secondary-color;
  text-decoration: none;
}

p {
  margin: 0.5rem;
  font-size: 1.6rem;
}

img {
  width: 100%;
}
</style>
