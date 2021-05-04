<template>
  <div class="contact">
    <div class="contact__overlay"></div>
    <div class="container">
      <h3>Feel free to contact me!</h3>
      <div class="contact__mail">
        <h3>contact@alexandresoares.fr</h3>
        <img
          class="icon"
          src="@/static/img/icon/copy.svg"
          alt="copy"
          @click.stop.prevent="copyTestingCode"
        />
        <input type="hidden" id="testing-code" :value="testingCode" />
      </div>
      <div v-if="successCopy" class="contact__message contact__success">
        You copied the email address!
      </div>
       <div v-if="successCopy === false" class="contact__message contact__error">
        Oops! Something's wrong!
      </div>
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
  data() {
    return {
      testingCode: 'contact@alexandresoares.fr',
      successCopy: null,
    }
  },
  methods: {
    copyTestingCode() {
      let testingCodeToCopy = document.querySelector('#testing-code')
      testingCodeToCopy.setAttribute('type', 'text') // 不是 hidden 才能複製
      testingCodeToCopy.select()

      try {
        var successful = document.execCommand('copy')
        var msg = successful ? 'successful' : 'unsuccessful'
        this.successCopy = true
      } catch (err) {
        this.successCopy = false
      }

      /* unselect the range */
      testingCodeToCopy.setAttribute('type', 'hidden')
      window.getSelection().removeAllRanges()
    },
  },
}
</script>

<style lang="scss" scoped>
.contact {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: relative;

  & .container {
    z-index: 2;
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
    color: white;
  }

  &__mail {
    text-align: center;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;

    & img {
      margin-left: 1rem;
      cursor: pointer;
    }

    & h3 {
      margin-right: 1rem;
    }
  }

  &__message {
    font-size: 1.4rem;
    padding: 1rem 2rem;
    border-radius: 0.5rem;
    display: block;
    width: 30rem;
    text-align: center;
    margin: 2rem auto;
  }

  &__success {
    background-color: #d4edda;
    color: #155724;
  }

  &__error {
    display: block;
    text-align: center;
    background-color: #f8d7da;
    color: #721c24;
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
    color: white;
  }
}
</style>
