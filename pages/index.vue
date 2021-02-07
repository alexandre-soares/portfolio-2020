<template>
  <div>
    <Intro />
    <Hero />
  </div>
</template>

<script>
import gsap from 'gsap'
import Hero from '../components/home/Hero.vue'
import Intro from '../components/home/Intro.vue'

export default {
  components: { Intro, Hero },
  mounted() {
    const tl = gsap.timeline({ defaults: { ease: 'power1.out' } })
    tl.to('.text', { y: '0%', duration: 1, stagger: 1.2 })
    tl.to('.slider', { y: '-100%', duration: 1.5, delay: 0.5, stagger: 0.1 })
    tl.to('.intro', { y: '-100%', duration: 1 }, '-=1')
    tl.fromTo('.navbar', { opacity: 0 }, { opacity: 1, duration: 1 })
  },
}
</script>

<style></style>
