<template>
  <div>
    <div class="intro">
      <div class="intro-text">
        <h1 class="hide">
          <span class="text">Meet your New Developer</span>
        </h1>
      </div>
    </div>
    <div class="slider"></div>
    <div class="slider slider--white"></div>
    <div class="slider slider--blue"></div>
  </div>
</template>

<script>
import gsap from 'gsap'
export default {
  name: 'Intro',
  mounted() {
    const tl = gsap.timeline({ defaults: { ease: 'power1.out' } })
    tl.to('.text', { y: '0%', duration: 1.3, stagger: 1.2 })
    tl.to('.slider', { x: '100%', duration: 1.1, delay: 0.5, stagger: 0.1 })
    tl.to('.intro', { y: '-100%', duration: 1 }, '-=1')
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

  &--white {
    z-index: 997;
    background: rgb(165, 121, 0);
  }

  &--blue {
    z-index: 996;
    background: rgb(43, 36, 133);
  }
}

.intro-text h1 {
  color: rgb(24, 24, 24);
  font-family: 'Aparey';
  font-size: 5rem;
  line-height: 1.7;
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
