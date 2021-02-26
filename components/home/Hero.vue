<template>
  <div id="hero" class="hero">
    <div class="container-fluid">
      <div class="row align-items-center">
        <div class="order-sm-12 order-lg-1 col-sm-12 col-lg-7">
          <div class="hero__title">
            <h1>Alexandre SOARES</h1>
            <h2>VueJS Web Developper</h2>
          </div>
        </div>
        <div class="order-sm-1 order-lg-12 col-sm-12 col-lg-5">
          <img
            class="hero__img"
            src="@/static/img/background/alex.jpg"
            alt="alex"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Hero',
}
</script>

<style lang="scss" scoped>
.hero {
  height: 100vh;
  padding: 0 10rem;
  display: flex;
  align-items: center;
  justify-content: center;
  /*
  background: url('../../static/img/background/alex.jpg');
  background-repeat: no-repeat;
  background-size: 40%;
  background-position-x: right;
  background-position-y: bottom;
  */

  &__title {
  }

  &__img {
    width: 100%;
    margin: 0 auto;
  }

  @media only screen and (max-width: $bp-small) {
    height: 100vh;
    text-align: center;
    padding: 0 1.5rem;
  }
}
</style>
