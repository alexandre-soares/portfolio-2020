<template>
  <div class="testimonies">
    <h2 class="mobile-title">Testimonies</h2>
    <div class="container">
      <div class="testimony">
        <img src="/img/testimonies/Doris.jpg" alt="Doris" />
        <blockquote class="groucho">
          I had the pleasure of working with Alex on two different projects over
          two years. Reactive and devoted to his work, Alex always navigated
          multi-partner projects with a lot of professionalism and a dash of
          humour.
          <footer>
            Doris MONJAC - Head Of The Economy And Society Unit of EUROQUALITY
          </footer>
        </blockquote>
      </div>
      <div class="testimony">
        <img src="/img/testimonies/Laura.jpg" alt="Laura" />
        <blockquote class="groucho">
          Alexandre is a great professional, very structured and organised. He
          was always doing his best to meet my requirements.
          <footer>Laura SIBILLE - UX-UI Designer</footer>
        </blockquote>
      </div>
    </div>
    <span class="background-title">Testimonies</span>
  </div>
</template>

<script></script>

<style lang="scss" scoped>
/* Some vars */
$background-color: hsl(50, 5, 97);
$black: hsl(200, 40, 10);
$white: $background-color;
$base-font-size: 1.8rem;
$base-line-height: 1.5em;

.testimonies {
  height: 100vh;
  position: relative;

  @media only screen and (max-width: $bp-small) {
    height: auto;
  }

  & .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
}

.testimony {
  margin: 10rem 0;
  display: flex;
  align-items: center;
  justify-content: center;

  @media only screen and (max-width: $bp-small) {
    margin: 5rem 0;
  }

  @media only screen and (max-width: $bp-medium) {
    align-items: flex-start;
  }

  & img {
    object-fit: cover;
    width: 15%;
    border-radius: 50%;
    margin-right: 2rem;

    @media only screen and (max-width: $bp-medium) {
      width: 30%;
    }
  }

  & p {
    width: 60%;
    text-align: justify;
  }

  & span {
    display: inline-block;
    color: #000046;
    margin-top: 2rem;
  }
}

.groucho {
  position: relative;
  font-size: $base-font-size;
  line-height: $base-line-height;
  width: 60%;

  footer {
    font-family: 'Noto Sans', sans-serif;
    font-size: 1.4rem;
    font-weight: 700;
    color: darken($white, 30%);
    float: right;

    &:before {
      content: '\2015';
    }
  }
  &:after {
    content: '\201D';
    position: absolute;
    top: 0.28em;
    right: -0.2em;
    font-size: 6em;
    font-style: italic;
    color: darken($white, 15%);
    z-index: -1;
  }
}
</style>
