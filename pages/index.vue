<template>
  <div>
    <Intro v-if="animate" />
    <Hero />
    <About />
    <Portfolio />
    <Contact />
  </div>
</template>

<script>
import gsap from 'gsap'
import Hero from '../components/home/Hero.vue'
import Intro from '../components/home/Intro.vue'
import About from '../components/home/About.vue'
import Portfolio from '../components/home/Portfolio.vue'
import Contact from '../components/home/Contact.vue'

export default {
  components: { Intro, Hero, About, Portfolio, Contact },
  data() {
    return {
      animate: true,
    }
  },
  mounted() {
    if (this.animate) {
      const tl = gsap.timeline({ defaults: { ease: 'power1.out' } })
      tl.to('.text', { y: '0%', duration: 1, stagger: 1.2 })
      tl.to('.slider', { y: '-100%', duration: 1.5, delay: 0.5, stagger: 0.1 })
      tl.to('.intro', { y: '-100%', duration: 1 }, '-=1')
      tl.fromTo('.navbar', { opacity: 0 }, { opacity: 1, duration: 1 })

      tl.fromTo('.hero', { opacity: 0 }, { opacity: 1, duration: 1 })
      tl.fromTo('.about', { opacity: 0 }, { opacity: 1, duration: 1 })
    }
  },
}
</script>

<style></style>
