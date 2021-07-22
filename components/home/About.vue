<template>
  <section class="about__wrapper">
    <div class="container">
      <div class="about">
        <h1 class="hide">
          <span class="text">Reliable.</span><span class="text">Versatile.</span
          ><span class="text">Organised.</span>
        </h1>
        <div class="about__plus">
          <p>
            In my previous experience, I developed several
            <strong>web-based applications</strong> for the European Commission.
            Their main goal was to
            <strong>introduce and highlight scientific innovations</strong> and
            breakthrough technologies
            <strong>enhancing daily life.</strong> Collaborating with
            consortiums made of several partners, I managed to build
            <strong>user-friendly</strong> and
            <strong>secure websites</strong> within the project frames, managing
            enhancement requests after each rollout.
          </p>
          <img
            src="/img/background/responsive-mockup-scene (1)-min.png"
            alt="img"
          />
        </div>
        <p>
          With solid <strong>work ethic</strong> and
          <strong>new technologies</strong>, I'm determined to produce quality
          products under deadline pressure. I smoothly manage projects from
          <strong>concept to completion.</strong>
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
          <div>
            <a
              href="https://getbootstrap.com/"
              target="_blank"
              rel="noopener noreferrer"
            >
              <img src="/img/icon/bootstrap.svg" alt="icon" />
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
          <div>
            <a
              href="https://firebase.google.com/?hl=FR"
              target="_blank"
              rel="noopener noreferrer"
            >
              <img src="/img/icon/firebase.png" alt="icon" />
            </a>
          </div>
          <div>
            <a
              href="https://www.atlassian.com/software/jira"
              target="_blank"
              rel="noopener noreferrer"
            >
              <img src="/img/icon/jira.png" alt="icon" />
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
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-top: 5rem;

  @media only screen and (max-width: $bp-small) {
    height: auto;
    padding-top: 2rem;
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

  &__plus {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;

    @media only screen and (max-width: $bp-large) {
      flex-direction: column;
    }

    & p {
      flex: 0 0 60%;
      z-index: 999;
    }

    & img {
      width: 50%;
      flex: 1;
      margin-left: 7rem;
      z-index: 800;

      @media only screen and (max-width: $bp-large) {
        margin-left: 0;
      }
    }
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

strong {
  transition: all 0.3s ease-in;
  &:hover {
    color: red;
  }
}

// Buttons

button {
  margin: 0 2rem;
  font-size: 1.6rem;
  font-family: 'Hind Guntur', sans-serif;
  line-height: 1;
  letter-spacing: 0.025em;
  padding: 1.1rem;
  cursor: pointer;
  color: white;
  border: 0;
  border-bottom: 1px solid $light-red;
  border-radius: 2px;
  min-width: 12rem;
  overflow: hidden;
  position: relative;
  background-color: transparent;
}

button a {
  display: block;
  position: relative;
  z-index: 10;
  transition: color 0.7s ease-in;
}

button:after,
button:before {
  padding: 1.1rem 0;
  content: '';
  position: absolute;
  top: 0;
  left: calc(-100% - 30px);
  height: 100%;
  width: calc(100% + 20px);
  color: #fff;
  border-radius: 2px;
  transform: skew(-25deg);
}

button:after {
  background: #fff;
  transition: left 0.8s cubic-bezier(0.86, 0, 0.07, 1) 0.2s;
  z-index: 0;
  opacity: 0.8;
}

button:before {
  background: $light-red;
  z-index: 5;
  transition: left 1s cubic-bezier(0.86, 0, 0.07, 1);
}

button:hover a {
  color: white !important;
}

button:hover:after {
  left: calc(0% - 10px);
  transition: left 0.8s cubic-bezier(0.86, 0, 0.07, 1);
}

button:hover:before {
  left: calc(0% - 10px);
  transition: left 1s cubic-bezier(0.86, 0, 0.07, 1);
}
</style>
