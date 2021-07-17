<template>
  <section class="about__wrapper">
    <div class="container">
      <div class="about">
        <h1 class="hide">
          <span class="text">Reliable.</span><span class="text">Versatile.</span
          ><span class="text">Organised.</span>
        </h1>
        <p>
          With solid work ethic, I'm determined to produce quality products
          under deadline pressure. I smoothly manage projects from concept to
          completion.
        </p>
        <div class="about__icons">
          <div>
            <a
              href="https://en.wikipedia.org/wiki/JavaScript"
              target="_blank"
              rel="noopener noreferrer"
            >
              <img src="/img/icon/js.svg" alt="icon" />
            </a>
          </div>
          <div>
            <a
              href="https://vuejs.org/"
              target="_blank"
              rel="noopener noreferrer"
            >
              <img src="/img/icon/vuejs.svg" alt="icon" />
            </a>
          </div>
          <div>
            <a
              href="https://fr.nuxtjs.org/"
              target="_blank"
              rel="noopener noreferrer"
            >
              <img src="/img/icon/nuxtjs.svg" alt="icon" />
            </a>
          </div>
          <div>
            <a
              href="https://sass-lang.com/"
              target="_blank"
              rel="noopener noreferrer"
            >
              <img src="/img/icon/sass.svg" alt="icon" />
            </a>
          </div>
        </div>
        <div class="about__icons">
          <div>
            <a
              href="https://code.visualstudio.com/"
              target="_blank"
              rel="noopener noreferrer"
            >
              <img src="/img/icon/vscode.svg" alt="icon" />
            </a>
          </div>
          <div>
            <a
              href="https://github.com/"
              target="_blank"
              rel="noopener noreferrer"
            >
              <img src="/img/icon/github.svg" alt="icon" />
            </a>
          </div>
          <div>
            <a
              href="https://nucleoapp.com/"
              target="_blank"
              rel="noopener noreferrer"
            >
              <img src="/img/icon/nucleo.png" alt="icon" />
            </a>
          </div>
          <div>
            <a
              href="https://www.postman.com/"
              target="_blank"
              rel="noopener noreferrer"
            >
              <img src="/img/icon/postman.svg" alt="icon" />
            </a>
          </div>
        </div>
        <div class="about__download">
          <button>
            <a target="_blank" href="/Alexandre Soares - Front Dev Resume.pdf"
              >Download My Resume</a
            >
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
// import gsap from 'gsap'
export default {
  name: 'About',
  mounted() {
    if (window.innerWidth > 600) {
      const scene = this.$scrollmagic
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
      text-align: justify;
    }
  }

  &__icons {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 50%;
    margin: 3rem 0;

    @media only screen and (max-width: $bp-small) {
      width: 80%;
    }

    & div {
      height: 6rem;
      width: 6rem;

      @media only screen and (max-width: $bp-small) {
        height: 4rem;
        width: 4rem;
      }
    }
  }

  &__download {
    margin-top: 3rem;
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
