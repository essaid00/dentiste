<template>
  <div
    class="hero-image bg-no-repeat bg-cover flex justify-center items-center"
  >
    <h1 class="h2 text-neutral-400">Dr. Mustapha ELMENDILI</h1>
  </div>
</template>

<style scoped lang="scss">
.hero-image {
  width: 100%;
  height: 100vh;
  background-image: url('https://afraid-else-dentisteapp-da324ef2.koyeb.app/dentiste.jpg');
  h1 {
    color: #fff;
    font-size: 72px;
    @media (max-width: $mobile-max-width) {
      font-size: 50px;
    }
  }
}
</style>
