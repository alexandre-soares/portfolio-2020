<template>
  <div class="contact">
    <div class="contact__overlay"></div>
    <div class="container">
      <h3>Feel free to contact me!</h3>
      <div class="contact__form__wrapper">
        <form class="contact__form" @submit.prevent="sendEmail">
          <div class="field">
            <label>Name</label>
            <input type="text" name="user_name" />
          </div>
          <div class="field">
            <label>Email</label>
            <input type="email" name="user_email" />
          </div>
          <div class="field">
            <label>Message</label>
            <textarea rows="10" name="message"></textarea>
          </div>
          <button class="btn" type="submit" value="Send">Send</button>
        </form>
        <div
          v-if="isEmailSent === true"
          class="contact__message contact__success"
        >
          You successfully sent the email!
        </div>
        <div
          v-if="isEmailSent === false"
          class="contact__message contact__success"
        >
          You successfully sent the email!
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
    }
  },
  methods: {
    sendEmail(e) {
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
            this.isEmailSent = true
          },
          (error) => {
            console.log(error)
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

    & .btn {
      padding: 1.5rem;
      margin: 2rem auto;
      width: 20%;
      background: #000046;
      text-align: center;
      display: block;
      transition: 500ms all ease-in;

      &:hover {
        background: #09096b;
      }

      &:after,
      &:before {
        content: none;
      }
    }
  }

  &__message {
    font-size: 1.4rem;
    padding: 1rem 2rem;
    border-radius: 0.5rem;
    display: block;
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
</style>
