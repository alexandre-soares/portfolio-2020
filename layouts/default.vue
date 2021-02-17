<template>
  <div>
    <Navbar />
    <Nuxt />
    <div v-if="customizeCursor" class="cursor"></div>
  </div>
</template>

<script>
import Navbar from '@/components/layout/Navbar.vue'
export default {
  components: {
    Navbar,
  },
  data() {
    return {
      customizeCursor: false,
    }
  },
  mounted() {
    if (this.customizeCursor) {
      const cursor = document.querySelector('.cursor')
      document.addEventListener('mousemove', (e) => {
        cursor.setAttribute(
          'style',
          'top: ' + (e.pageY - 20) + 'px; left: ' + (e.pageX - 20) + 'px'
        )
      })

      document.addEventListener('click', () => {
        cursor.classList.add('cursor--expand')

        setTimeout(() => {
          cursor.classList.remove('cursor--expand')
        }, 500)
      })
    }
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

  @media only screen and (max-width: $bp-medium) {
    font-size: 61%;
  }

  @media only screen and (max-width: $bp-small) {
    font-size: 60%;
  }

  @media only screen and (max-width: $bp-smallest) {
    font-size: 58%;
  }
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
  position: relative;
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

h1 {
  font-size: 4rem;
  font-weight: 400;
  letter-spacing: 1px;
}

h2 {
  font-size: 3.5rem;
  font-weight: 200;
  margin: 2rem 0 2.5rem;
}

h3 {
}

a {
  color: $secondary-color;
  text-decoration: none;
}

p {
  margin: 0.5rem;
  font-size: 1.6rem;
  line-height: 1.7;
}

img {
  width: 100%;
}

// btn

.btn {
  padding: 1rem 2rem;
  background-color: $secondary-color;
  border: none;
  border-radius: 1rem;
  display: inline-block;
  margin: 2rem 0;
  color: $primary-color;
  font-size: 1.6rem;
  cursor: pointer;
}

// icons

.icon {
  width: 4rem;
  height: 4rem;
}

// cursor

.cursor {
  width: 40px;
  height: 40px;
  border: 2px solid white;
  border-radius: 50%;
  position: absolute;

  transition-duration: 200ms;
  transition-timing-function: ease-out;
  animation: cursorAnimation 0.7s infinite alternate;

  &::after {
    content: '';
    width: 60px;
    height: 60px;
    border: 8px solid grey;
    border-radius: 50%;
    position: absolute;
    opacity: 0.5;
    top: -12px;
    left: -12px;
    animation: cursorAnimation2 0.6s infinite alternate;
  }

  &--expand {
    animation: cursorAnimation3 0.5s forwards;
    border: 1px solid red;
  }
}

@keyframes cursorAnimation {
  from {
    transform: scale(1);
  }

  to {
    transform: scale(0.7);
  }
}

@keyframes cursorAnimation2 {
  from {
    transform: scale(1);
  }

  to {
    transform: scale(0.4);
  }
}

@keyframes cursorAnimation3 {
  0% {
    transform: scale(1);
  }

  50% {
    transform: scale(3);
  }

  100% {
    transform: scale(1);
    opacity: 0;
  }
}

/* Enter and leave animations can use different */
/* durations and timing functions.              */
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}

// STYLE CAROUSEL

.slick-dots li button:before {
  color: $light-red !important;
  font-size: 1.8rem !important;
  margin-right: 2rem;
}

// Title Lines

.title-line {
  width: 50px;
  height: 2px;
  display: inline-block;
  border: 1px solid white;
  margin-right: 30px;
}
</style>
