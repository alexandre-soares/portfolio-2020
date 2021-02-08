<template>
  <div class="portfolio">
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <h2 class="portfolio__title">Portfolio</h2>
        </div>
      </div>
      <div class="row">
        <div class="col">
          <div class="card">
            <div class="card__img">
              <img src="@/static/img/portfolio/laura-sibille.png" alt="img" />
            </div>
            <div class="card__title"><h3>Website</h3></div>
          </div>
        </div>
        <div class="col">
          <div class="card">
            <div class="card__img">
              <img src="@/static/img/portfolio/laura-sibille.png" alt="img" />
            </div>
            <div class="card__title"><h3>Website</h3></div>
          </div>
        </div>
        <div class="col">
          <div class="card">
            <div class="card__img">
              <img src="@/static/img/portfolio/laura-sibille.png" alt="img" />
            </div>
            <div class="card__title"><h3>Website</h3></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Portfolio',
}
</script>

<style lang="scss" scoped>
.portfolio {
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
}

.card {
  position: relative;
  cursor: pointer;
  filter: grayscale(1);
  transition: 0.3s ease-in;

  &:hover {
    filter: grayscale(0);
  }

  &__title {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);

    & h3 {
      font-size: 5rem;
      letter-spacing: 5px;
      font-weight: 200;
    }
  }
}
</style>
