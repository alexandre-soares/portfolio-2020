<template>
  <div id="about" class="about">
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <h2>About Me</h2>
        </div>
      </div>
      <div class="row">
        <div class="col-sm-12 col-lg-6">
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
        <div class="col-sm-12 col-lg-6">
          <div class="row">
            <div class="col label__wrapper">
              <h3>Languages</h3>
              <span class="label label--html"><span>H</span>tml</span>
              <span class="label label--css"><span>C</span>ss</span>
              <span class="label label--javascript"
                ><span>J</span>avascript</span
              >
              <span class="label label--sass"><span>S</span>ass</span>
              <h3>Frameworks</h3>
              <span class="label label--vuejs"><span>V</span>ueJS</span>
              <span class="label label--nuxtjs"><span>N</span>uxtJS</span>
              <h3>Softwares</h3>
              <span class="label label--vscode"><span>V</span>S Code</span>
              <span class="label label--github"><span>G</span>ithub</span>
              <span class="label label--nucleo"><span>N</span>ucleo</span>
              <span class="label label--postman"><span>P</span>ostman</span>
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
  height: 100vh;
  padding: 0 10rem;
  display: flex;
  align-items: center;
  justify-content: center;
  @media only screen and (max-width: $bp-small) {
    height: auto;
    padding: 0 1.5rem;
  }

  & p {
    text-align: justify;
    margin-top: 0;
  }

  & h3 {
    font-size: 2.5rem;
    font-weight: 400;
    letter-spacing: 2px;
    margin: 2rem 0;

    &:first-child {
      margin-top: 0;
    }
  }
}
</style>
