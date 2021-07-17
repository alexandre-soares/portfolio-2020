<template>
  <div>
    <Nuxt />
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss">
html {
  font-family: Roboto, 'Helvetica Neue', Arial, sans-serif;
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
  height: 100%;
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

.slick-slider {
  width: 80%;
  margin: 0 auto;
}

// Title Lines

.section-title {
  @media only screen and (max-width: $bp-small) {
    margin: 0 auto;
  }
}

.title-line {
  width: 50px;
  height: 2px;
  display: inline-block;
  border: 1px solid white;
  margin-right: 30px;
}

// Background Title

.background-title {
  position: absolute;
  bottom: 0;
  right: 2rem;
  color: rgba(78, 78, 78, 0.2);
  font-size: 10rem;

  @media only screen and (max-width: $bp-small) {
    display: none;
  }
}

// Mobile title

.mobile-title {
  padding: 4rem 0;
  background: -webkit-linear-gradient(
    to right,
    #000046,
    #1cb5e0
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #000046,
    #1cb5e0
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  color: white;
  margin: 3rem 0;
  text-align: center;
  display: none;
  font-size: 4rem;
  font-weight: bold;

  @media only screen and (max-width: $bp-small) {
    display: block;
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
