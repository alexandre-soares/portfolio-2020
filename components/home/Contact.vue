<template>
  <div class="contact">
    <div class="container">
      <h3>Feel free to contact me!</h3>
      <div class="contact__links">
        <div class="contact__card">
          <a href="https://www.linkedin.com/in/alex-ds-soares/" target="_blank">
            <img src="@/static/img/icon/linkedin-white.svg" alt="linkedin" />
            <span class="contact__card-title">Linkedin</span>
          </a>
        </div>
        <div class="contact__card">
          <a href="mailto:contact@alexandresoares.fr">
            <img src="@/static/img/icon/mail-white.svg" alt="linkedin" />
            <span class="contact__card-title">Mail</span>
          </a>
        </div>
      </div>
    </div>
    <span class="background-title">Contact</span>
  </div>
</template>

<script>
export default {
  name: 'Contact',
}
</script>

<style lang="scss" scoped>
.contact {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;

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

  &__links {
    width: 30%;
    margin: auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
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
      width: 4rem;
      height: 4rem;
    }
  }

  &__card-title {
    display: inline-block;
    margin-top: 2rem;
    font-size: 1.4rem;
  }
}
</style>
