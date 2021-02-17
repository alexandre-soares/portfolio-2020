<template>
  <div class="other-projects">
    <div class="container">
      <div class="row align-items-center">
        <span class="title-line"></span>
        <h2>Other Projects</h2>
      </div>
      <div class="row align-items-center justify-content-start">
        <div class="project col-4">
          <div class="project__card">
            <div class="project__img"></div>
            <div class="project__title">Mario</div>
            <div class="project__link">
              <a href="#">Github</a>
            </div>
          </div>
        </div>
        <div class="project col-4">
          <div class="project__card">
            <div class="project__img"></div>
            <div class="project__title">Mario</div>
            <div class="project__link">
              <a href="#">Github</a>
            </div>
          </div>
        </div>
        <div class="project col-4">
          <div class="project__card">
            <div class="project__img"></div>
            <div class="project__title">Mario</div>
            <div class="project__link">
              <a href="#">Github</a>
            </div>
          </div>
        </div>
        <div class="project col-4">
          <div class="project__card">
            <div class="project__img"></div>
            <div class="project__title">Mario</div>
            <div class="project__link">
              <a href="#">Github</a>
            </div>
          </div>
        </div>
        <div class="project col-4">
          <div class="project__card">
            <div class="project__img"></div>
            <div class="project__title">Mario</div>
            <div class="project__link">
              <a href="#">Github</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.other-projects {
  background-color: black;
}

.project {
  text-align: center;
  margin: 2rem 0;
  &__card {
  }

  &__img {
    height: 20rem;
    width: 20rem;
    background-color: white;
    border-radius: 0.5rem;
    overflow: hidden;
    margin: 1rem auto;
  }

  &__title {
  }

  &__link {
    & a {
      margin-top: 2rem;
      display: inline-block;
      padding: 1rem 2rem;
      font-size: 1.6rem;
      border-bottom: 1px solid $light-red;
    }
  }
}
</style>
