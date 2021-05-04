<template>
  <section class="about__wrapper">
    <div class="container">
      <div class="about">
        <div>
          <h1>Reliable. Versatile.</h1>
          <p>
            With solid work ethic I'm determined to produce quality products
            under deadline pressure. I smoothly manages projects from concept to
            completion and i'm adept at problem solving at ease working with
            team or independently.
          </p>
          <span class="label label--sass"><span>S</span>ass</span>
          <span class="label label--javascript"><span>J</span>avascript</span>
          <span class="label label--vuejs"><span>V</span>ueJS</span>
          <span class="label label--nuxtjs"><span>N</span>uxtJS</span>
          <br />
          <span class="label label--vscode"><span>V</span>S Code</span>
          <span class="label label--github"><span>G</span>ithub</span>
          <span class="label label--nucleo"><span>N</span>ucleo</span>
          <span class="label label--postman"><span>P</span>ostman</span>
        </div>
        <div class="about__background">
          <img src="@/static/img/background/me.png" alt="background" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'About',
}
</script>

<style lang="scss" scoped>
.about {
  display: grid;
  grid-gap: 3rem;
  grid-template-columns: 1fr 1fr;

  &__wrapper {
    padding: 5rem 3rem;
    display: flex;
    align-items: center;
    justify-content: center;
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
  }

  & p {
    text-align: justify;
    margin: 3rem 0;
  }
}
</style>
