<template>
  <div>
    <Intro class="intro" />
    <Hero />
    <About />
    <Projects />
    <Testimonies />
    <Contact />
  </div>
</template>

<script>
import Intro from '../components/home/Intro.vue'
import Hero from '../components/home/Hero.vue'
import About from '../components/home/About.vue'
import Projects from '../components/home/Projects.vue'
import Contact from '../components/home/Contact.vue'
import Testimonies from '../components/home/Testimonies.vue'

export default {
  components: { Intro, Hero, About, Projects, Contact, Testimonies },
  data() {
    return {}
  },
}
</script>

<style lang="scss" scoped>
.intro {
  z-index: 999;
}
</style>
