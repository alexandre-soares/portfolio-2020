<template>
  <div class="hero">
    <div class="hero__bg-white"></div>
    <div class="hero__overlay"></div>
    <div class="container">
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
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.hero {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: flex-start;

  background: url('../../static/img/background/alex.png'); /* Chrome 10-25, Safari 5.1-6 */
  background-position: center right;
  background-repeat: no-repeat;
  background-size: contain;

  position: relative;

  @media only screen and (max-width: $bp-small) {
    text-align: center;
    background-position: center center;
    background-size: cover;
  }

  & .container {
    z-index: 1;
  }

  &__overlay {
    position: absolute;
    opacity: 0.7;
    height: 100%;
    width: 100%;
    background: #000046; /* fallback for old browsers */
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
  }

  &__titles {
    & h1,
    h2 {
      color: white;
      z-index: 100;
    }
  }

  & h2 {
    margin: 4rem 0;
  }

  &__contact {
    text-align: center;
    width: 40%;
    display: grid;
    grid-gap: 3rem;
    grid-template-columns: 1fr 1fr 1fr;

    @media only screen and (max-width: $bp-small) {
      margin: 0 auto;
      width: 70%;
    }

    & a {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-between;
    }

    & img {
      width: 3rem;
    }

    & span {
      font-size: 1.4rem;
      color: white;
      margin-top: 1rem;
    }
  }
}
</style>
