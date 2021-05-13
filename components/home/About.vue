<template>
  <section class="about__wrapper">
    <div class="container">
      <div class="about">
        <h1 class="hide">
          <span class="text">Reliable.</span><span class="text">Versatile.</span
          ><span class="text">Organised.</span>
        </h1>
        <p>
          With solid work ethic, I'm determined to produce quality products under
          deadline pressure. I smoothly manages projects from concept to
          completion and i'm adept at problem solving at ease working with team
          or independently.
        </p>
        <div class="about__labels">
          <span class="label"><span>S</span>ass</span>
          <span class="label"><span>J</span>avascript</span>
          <span class="label"><span>V</span>ueJS</span>
          <span class="label"><span>N</span>uxtJS</span>
          <br />
          <span class="label"><span>V</span>S Code</span>
          <span class="label"><span>G</span>ithub</span>
          <span class="label"><span>N</span>ucleo</span>
          <span class="label"><span>P</span>ostman</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import gsap from 'gsap'
export default {
  name: 'About',
  mounted() {
    var tl = gsap.timeline({ defaults: { ease: 'power1.out' } })

    if (window.innerWidth > 600) {
      var scene = this.$scrollmagic
        .scene({
          triggerElement: '.about',
          triggerHook: 0,
          duration: 1000,
        })
        .setPin('.about')
        .setTween('.text', 1, { y: '0', stagger: 1 })


      this.$scrollmagic.addScene(scene)
    }
  },
}
</script>
<style lang="scss" scoped>
.about {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  @media only screen and (max-width: $bp-small) {
    height: auto;
  }

  &__wrapper {
    padding: 5rem 3rem;
    position: relative;

    @media only screen and (max-width: $bp-small) {
      height: auto;
      padding: 0 1.5rem;
    }
  }

  &__background {
    border-left: 3rem solid #000046;
  }

  & h1 {
    font-size: 3.9rem;
    margin: 3rem 0;
    text-align: center;
  }

  & p {
    text-align: justify;
    margin: 10rem auto;
    font-size: 1.9rem;
    width: 70%;
    letter-spacing: 2px;
    line-height: 1.9;

    @media only screen and (max-width: $bp-small) {
      width: 90%;
      margin: 5rem auto;
      text-align: center;
    }
  }

  &__labels {
    text-align: center;
  }
}

.text {
  font-family: 'Heebo', sans-serif;
  font-size: 7rem;
  margin: 0 1rem;

  @media only screen and (max-width: $bp-small) {
    font-size: 5rem;
    margin: 1rem;
  }
}

.hide {
  background-color: $primary-color;
  overflow: hidden;

  @media only screen and (max-width: $bp-small) {
    overflow: visible;
    background-color: transparent;
  }
}

.hide span {
  transform: translateY(100%);
  display: inline-block;

  @media only screen and (max-width: $bp-small) {
    display: block;
  }
}
</style>
