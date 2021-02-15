<template>
  <div id="contact" class="contact">
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <h2>Contact</h2>
        </div>
      </div>
      <div class="row">
        <div class="col">
          <h3>Interested? Do not hesitate to contact me!</h3>
        </div>
      </div>
      <div class="row justify-content-center align-items-center">
        <div class="col-2 col-lg-1">
          <div class="contact__card">
            <a
              href="https://www.linkedin.com/in/alex-ds-soares/"
              target="_blank"
            >
              <img src="@/static/img/icon/linkedin-white.svg" alt="linkedin" />
              <span class="contact__card-title">Linkedin</span>
            </a>
          </div>
        </div>
        <div class="col-2 col-lg-1">
          <div class="contact__card">
            <a href="mailto:contact@alexandresoares.fr">
              <img src="@/static/img/icon/mail-white.svg" alt="linkedin" />
              <span class="contact__card-title">Mail</span>
            </a>
          </div>
        </div>
        <div class="col-2 col-lg-1">
          <div class="contact__card">
            <a href="https://github.com/alexandre-soares" target="_blank">
              <img src="@/static/img/icon/github-white.svg" alt="github" />
              <span class="contact__card-title">Github</span>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact',
}
</script>

<style lang="scss" scoped>
.contact {
  //height: 100vh;
  padding: 0 10rem;
  display: flex;
  align-items: center;
  justify-content: center;

  @media only screen and (max-width: $bp-small) {
    height: auto;
    padding: 0 1.5rem;
  }

  & p {
    line-height: 1.6;
    font-size: 2rem;
    text-align: justify;
  }

  & h3 {
    font-size: 2.4rem;
    font-style: italic;
    font-weight: 300;
    letter-spacing: 2px;
    text-align: center;
    margin: 2rem 0;
  }

  &__card {
    margin: 2rem;
    text-align: center;

    & a {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    & img {
      width: 100%;
      height: 100%;
    }
  }

  &__card-title {
    display: inline-block;
    margin-top: 2rem;
    font-size: 1.4rem;
  }
}
</style>
