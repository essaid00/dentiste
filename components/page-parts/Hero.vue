<template>
  <div
    class="hero-image bg-no-repeat bg-cover flex justify-center items-center"
  >
    <h1 class="h2 text-white">YUSHI WATANABE</h1>
  </div>
</template>

<style scoped lang="scss">
.hero-image {
  width: 100%;
  height: 100vh;
  background-image: url('./hero.jpg');
  h1 {
    color: #fff;
    font-size: 72px;
    @media (max-width: $mobile-max-width) {
      font-size: 50px;
    }
  }
}
</style>
