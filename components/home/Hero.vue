<template>
  <div class="hero">
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <div class="hero__title">
            <h1>Alexandre SOARES</h1>
            <h2>UX Engineer</h2>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam
              provident asperiores laudantium velit rerum? Maxime, hic. Odit,
              aspernatur nihil consectetur tempora velit deserunt? Quam
              laboriosam impedit, atque placeat sapiente assumenda.
            </p>
          </div>
        </div>
        <div class="col">
          <div class="hero__img">
            <img src="" alt="" />
          </div>
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
  height: 60vh;
  padding: 0 10rem;
  display: flex;
  align-items: center;
  justify-content: center;

  &__title {
    & h1 {
      font-size: 7rem;
      margin: 2rem 0;
      font-weight: 400;
      letter-spacing: 1px;
    }

    & h2 {
      font-size: 5rem;
      font-weight: 200;
      margin: 2rem 0 5rem;
    }

    & p {
      line-height: 1.6;
      font-size: 2rem;
    }
  }
}
</style>
