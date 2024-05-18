<template>
  <li class="card-wrap">
    <a :href="url" target="_blank" class="p-5 flex flex-col items-center">
      <h3 class="h3">{{ title }}</h3>
      <div class="card-content mb-3 self-stretch">
        <img :src="filePath" class="image" />
        <div class="flex flex-col">
          <p v-if="techStacks.length">{{ techStacks.join(', ') + '。' }}</p>
          <p class="description">{{ description }}</p>
        </div>
      </div>
      <small class="url">{{ url }}</small>
    </a>
  </li>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: '',
    },
    url: {
      type: String,
      default: '',
    },
    description: {
      type: String,
      default: '',
    },
    techStacks: {
      type: Array,
      default: () => [],
    },
    fileName: {
      type: String,
      default: '',
    },
  },
  computed: {
    filePath() {
      return 'links/' + this.fileName
    },
  },
}
</script>

<style lang="scss" scoped>
* {
  text-align: left;
  text-decoration: none;
}
.card-wrap {
  background-color: #fff;
  transition: 0.5s;
  &:hover {
    box-shadow: 0 0 50px -10px $gray-2;
    transition: 0.5s;
  }
}
.card-content {
  display: flex;
  flex-direction: row;
  @media (max-width: $mobile-max-width) {
    flex-direction: column;
    align-items: center;
    * {
      text-align: center;
    }
  }
}
.h3 {
  border-bottom: solid $text-1 1px;
  margin-bottom: 25px;
}
.image {
  height: 150px;
  width: 150px;
  object-fit: contain;
  border: solid 1px $gray-3;
  margin-right: 12px;

  @media (max-width: $mobile-max-width) {
    margin-right: 0;
    margin-bottom: 12px;
    height: auto;
    min-width: 80%;
  }
}
.url {
  width: 100%;
  font-size: 12px;
  text-align: center;
  color: $gray-2;
  word-wrap: break-word;
}
</style>
