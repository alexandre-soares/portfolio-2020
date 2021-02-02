<template>
  <div>
    <div class="intro">
      <div class="intro-text">
        <h1 class="hide">
          <span class="text">When Design</span>
        </h1>
        <h1 class="hide">
          <span class="text">Meets Productivity</span>
        </h1>
      </div>
    </div>
    <div class="slider"></div>
  </div>
</template>

<style lang="scss" scoped>
.intro {
  background: $primary-color;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.slider {
  background: rgb(97, 105, 109);
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transform: translateY(100%);
}

.intro-text {
  color: rgb(233, 233, 233);
  font-family: 'Aparey';
  font-size: 4rem;
  line-height: 1.7;
}

.hide {
  background-color: $primary-color;
  overflow: hidden;
}

.hide span {
  transform: translateY(100%);
  display: inline-block;
}
</style>
