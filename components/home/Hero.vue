<template>
  <div id="hero" class="hero">
    <div class="container-fluid">
      <div class="row">
        <div class="col-sm-12 col-lg-4">
          <div class="hero__title">
            <h1>Alexandre SOARES</h1>
            <h2>VueJS Web Developper</h2>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam
              provident asperiores laudantium velit rerum? Maxime, hic. Odit,
              aspernatur nihil consectetur tempora velit deserunt? Quam
              laboriosam impedit, atque placeat sapiente assumenda.
            </p>
          </div>
        </div>
        <div class="col-lg">
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
  height: 100vh;
  padding: 0 10rem;
  display: flex;
  align-items: center;
  justify-content: center;

  @media only screen and (max-width: $bp-small) {
    height: 100vh;
    padding: 0 1.5rem;
  }
}
</style>
