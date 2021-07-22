<template>
  <div class="contact">
    <div class="contact__overlay"></div>
    <div class="container">
      <h3>Feel free to contact me!</h3>
      <div class="contact__form__wrapper">
        <form class="contact__form" @submit.prevent="sendEmail">
          <div class="field">
            <label>Name</label>
            <input type="text" name="user_name" required />
          </div>
          <div class="field">
            <label>Email</label>
            <input type="email" name="user_email" required />
          </div>
          <div class="field">
            <label>Message</label>
            <textarea rows="10" name="message"></textarea>
          </div>
          <button
            type="submit"
            class="button"
            value="Send"
            :class="{ 'button--loading': loadingButton }"
          >
            <span class="button__text">Send</span>
          </button>
        </form>
        <div
          v-if="isEmailSent === true"
          class="contact__message contact__message--success"
        >
          Thank you ! You successfully sent the message!
        </div>
        <div
          v-if="isEmailSent === false"
          class="contact__message contact__message--error"
        >
          Oops! Something's wrong!
        </div>
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
        <div class="contact__card">
          <a href="https://github.com/alexandre-soares" target="_blank">
            <img src="@/static/img/icon/github-white.svg" alt="github" />
            <span class="contact__card-title">Github</span>
          </a>
        </div>
      </div>
    </div>
    <span class="background-title">Contact</span>
  </div>
</template>

<script>
import emailjs from 'emailjs-com'
export default {
  name: 'Contact',
  data() {
    return {
      isEmailSent: null,
      loadingButton: null,
    }
  },
  methods: {
    sendEmail(e) {
      this.loadingButton = true
      emailjs
        .sendForm(
          'service_wjep9cc',
          'template_mnlhg61',
          e.target,
          'user_Zi0oEySIEQtJvHwy02QhL'
        )
        .then(
          (result) => {
            console.log(result)
            this.loadingButton = false
            this.isEmailSent = true
          },
          (error) => {
            console.log(error)
            this.loadingButton = false
            this.isEmailSent = false
          }
        )
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
      45deg,
      #000046,
      #1cb5e0
    ); /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(
      45deg,
      #000046,
      #1cb5e0
    ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  }

  & h3 {
    font-size: 2.6rem;
    font-style: italic;
    font-weight: 300;
    letter-spacing: 2px;
    text-align: center;
    margin: 2rem 0;
    color: white;
  }

  &__form {
    margin: 2rem auto;
    display: block;
    width: 100%;

    &__wrapper {
      width: 100%;
      margin: 0 auto;
    }

    & .field {
      margin: 2rem auto;
    }

    & label {
      display: block;
      margin: 1rem 0;
      font-size: 1.6rem;
      color: #fff;
    }

    & input,
    textarea {
      width: 100%;
      padding: 1rem 2rem;
      font-size: 1.6rem;
      border-radius: 0.5rem;
      border: none;
      font-family: Roboto, 'Helvetica Neue', Arial, sans-serif;
    }
  }

  &__message {
    font-size: 1.4rem;
    padding: 1rem 2rem;
    border-radius: 0.5rem;
    display: block;
    text-align: center;
    margin: 2rem auto;

    &--success {
      background-color: #d4edda;
      color: #155724;
    }

    &--error {
      display: block;
      text-align: center;
      background-color: #f8d7da;
      color: #721c24;
    }
  }

  &__links {
    width: 50%;
    margin: auto;
    display: flex;
    align-items: center;
    justify-content: space-around;

    @media only screen and (max-width: $bp-small) {
      width: 50%;
    }
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

.button {
  padding: 1.5rem;
  margin: 2rem auto;
  width: 20%;
  font-size: 1.6rem;
  background: #000046;
  text-align: center;
  display: block;
  position: relative;
  border: none;
  border-radius: 1rem;
  outline: none;
  cursor: pointer;
}

.button:active {
  background: #000046;
}

.button__text {
  color: #ffffff;
  transition: all 0.2s;
}

.button--loading .button__text {
  visibility: hidden;
  opacity: 0;
}

.button--loading::after {
  content: '';
  position: absolute;
  width: 16px;
  height: 16px;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  margin: auto;
  border: 4px solid transparent;
  border-top-color: #ffffff;
  border-radius: 50%;
  animation: button-loading-spinner 1s ease infinite;
}

@keyframes button-loading-spinner {
  from {
    transform: rotate(0turn);
  }

  to {
    transform: rotate(1turn);
  }
}
</style>
