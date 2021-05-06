<template>
  <section>
    <div class="intro">
      <div class="intro-text">
        <h1 class="hide">
          <span class="text">Meet your New Developer</span>
        </h1>
      </div>
    </div>
    <div class="slider"></div>
    <div class="slider slider--orange"></div>
    <div class="slider slider--blue"></div>
  </section>
</template>

<script>
import gsap from 'gsap'
export default {
  name: 'Intro',
  mounted() {
    const tl = gsap.timeline({ defaults: { ease: 'power1.out' } })
    tl.to('.text', { y: '0%', duration: 1.4, })
    tl.to('.slider', { x: '100%', duration: 1.1, stagger: 0.25, delay: 1.2 })
    tl.to('.text', { y: '100%', duration: 1.4, }, '-=1')
    tl.to('.intro', { opacity: 0, duration: 1 }, '-=1')
    tl.to('.intro', { y: '100%', duration: .1 })
  },
}
</script>

<style lang="scss" scoped>
.intro {
  background: $primary-color;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.slider {
  background: rgb(97, 105, 109);
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transform: translateX(-100%);
  z-index: 998;
  clip-path: polygon(25% 0%, 100% 0%, 75% 100%, 0% 100%);

  &--orange {
    z-index: 997;
    background: #000046;
  }

  &--blue {
    z-index: 996;
    background: #1cb5e0;
  }
}

.intro-text h1 {
  color: rgb(24, 24, 24);
  font-family: 'Aparey';
  font-size: 5rem;
  line-height: 1.7;
  text-align: center;
}

.hide {
  background-color: $primary-color;
  overflow: hidden;
}

.hide span {
  transform: translateY(100%);
  display: inline-block;
}
</style>
