<template>
  <div class="contact">
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <h2 class="contact__title">Contact</h2>
        </div>
      </div>
      <div class="row">
        <div class="col">
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Pariatur
            est sit fugit ut eligendi cum? Odio facilis provident voluptatum,
            amet ducimus commodi pariatur magnam ipsam quia, libero veniam minus
            nobis. Lorem, ipsum dolor sit amet consectetur adipisicing elit.
            Voluptates illum nihil autem, vel aperiam quis, ipsam suscipit,
            earum repellat ea quod accusamus quia maiores ipsum quibusdam dolor
            consectetur sit quisquam?
          </p>
        </div>
      </div>
      <div class="row justify-content-center align-items-center">
        <div class="col-1">
          <div class="contact__card">
            <img src="@/static/img/icon/linkedin-white.svg" alt="linkedin" />
            <span class="contact__card-title">Linkedin</span>
          </div>
        </div>
        <div class="col-1">
          <div class="contact__card">
            <img src="@/static/img/icon/mail-white.svg" alt="linkedin" />
            <span class="contact__card-title">Mail</span>
          </div>
        </div>
        <div class="col-1">
          <div class="contact__card">
            <img src="@/static/img/icon/github-white.svg" alt="github" />
            <span class="contact__card-title">Github</span>
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
  height: 60vh;
  padding: 0 10rem;
  display: flex;
  align-items: center;
  justify-content: center;

  &__title {
    font-size: 5rem;
    font-weight: 200;
    margin: 2rem 0 5rem;
  }

  & p {
    line-height: 1.6;
    font-size: 2rem;
    text-align: justify;
  }

  &__card {
    margin: 2rem;
    text-align: center;
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
