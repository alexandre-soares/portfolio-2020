<template>
  <div class="about">
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <h2 class="about__title">About Me</h2>
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
        <div class="col">
          <div class="row">
            <div class="col label__wrapper">
              <span class="label label--javascript"
                ><span>J</span>avascript</span
              >
              <span class="label label--vuejs"><span>V</span>ueJS</span>

              <span class="label label--nuxtjs"><span>N</span>uxtJS</span>
              <div class="label label--sass"><span>S</span>ass</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
}
</script>

<style lang="scss" scoped>
.about {
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
}

.label {
  background-color: white;
  color: black;
  padding: 1rem 3rem;
  font-size: 1.5rem;
  border-radius: 50rem;
  text-transform: uppercase;
  display: inline-block;
  margin: 1rem;
  text-align: center;

  &__wrapper {
    text-align: center;
  }

  & span {
    font-size: 2rem;
  }

  &--javascript {
    background-color: #e4a126;
    color: white;
  }

  &--vuejs {
    background: #00c58e;
    color: white;
  }

  &--nuxtjs {
    background: #2f495e;
    color: white;
  }

  &--sass {
    background: #ce6b9e;
    color: white;
  }
}
</style>
