<template>
  <div>
    <Navbar />
    <Nuxt />
  </div>
</template>

<script>
import Navbar from '@/components/layout/Navbar.vue'
// import gsap from 'gsap'
export default {
  components: {
    Navbar,
  },
  mounted() {

    const tl = gsap.timeline({ defaults: { ease: 'power1.out' } })

    tl.to('.text', { y: '0%', duration: 1, stagger: 1.2 })
    tl.to('.slider', { y: '-100%', duration: 1.5, delay: 0.5, stagger: 0.1})
    tl.to('.intro', { y: '-100%', duration: 1 }, '-=1')
    tl.fromTo('.navbar', { opacity: 0 }, { opacity: 1, duration: 1 })

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
