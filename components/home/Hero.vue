<template>
  <div class="hero">
    <div class="hero__titles">
      <h1>Alexandre SOARES</h1>
      <h2>VueJS Web Developer</h2>
      <div class="hero__contact">
        <a href="https://www.linkedin.com/in/alex-ds-soares/" target="_blank">
          <img src="@/static/img/icon/linkedin-white.svg" alt="linkedin" />
          <span>Linkedin</span>
        </a>
        <a href="mailto:contact@alexandresoares.fr">
          <img src="@/static/img/icon/mail-white.svg" alt="linkedin" />
          <span>Mail</span>
        </a>
        <a href="https://github.com/alexandre-soares" target="_blank">
          <img src="@/static/img/icon/github-white.svg" alt="github" />
          <span>Github</span>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.hero {
  padding: 0 3rem;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: flex-start;

  background: #2980b9; /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #2980b9, #ffffff),
    url('../../static/img/background/alex.jpg'); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #2980b9, #ffffff),
    url('../../static/img/background/alex.jpg'); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  background-position: center, center right;
  background-repeat: no-repeat, no-repeat;
  background-size: cover, 50%;

  background-blend-mode: multiply;

  &__titles {
    & h1,
    h2 {
      color: white;
    }
  }

  &__contact {
    text-align: center;
    width: 40%;
    display: grid;
    grid-gap: 3rem;
    grid-template-columns: 1fr 1fr 1fr;

    & img {
      width: 3rem;
    }

    & span {
      font-size: 1.4rem;
      color: white;
    }
  }
}
</style>
