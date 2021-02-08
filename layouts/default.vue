<template>
  <div>
    <Navbar />
    <Nuxt />
    <div class="cursor"></div>
  </div>
</template>

<script>
import Navbar from '@/components/layout/Navbar.vue'
export default {
  components: {
    Navbar,
  },
  mounted() {
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

// cursor

.cursor {
  width: 40px;
  height: 40px;
  border: 1px solid white;
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
    top: -11px;
    left: -11px;
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
</style>
