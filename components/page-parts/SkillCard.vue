<template>
  <li class="card-wrap">
    <h3 class="h3 mb-2">{{ title }}</h3>
    <p class="experience mb-1">{{ experience }}</p>
    <p class="description">{{ description }}</p>
  </li>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: '',
    },
    experience: {
      type: String,
      default: '',
    },
    description: {
      type: String,
      default: '',
    },
  },
}
</script>

<style lang="scss" scoped>
.card-wrap {
  margin-bottom: 20px;
  padding: 15px 20px;
  border: solid 1px $gray-3;
  border-radius: 10px;
  .experience {
    font-size: 14px;
    font-weight: bold;
  }
}
</style>
