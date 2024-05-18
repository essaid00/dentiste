<template>
  <div
    class="nav-modal flex justify-center items-center"
    :class="navClass"
    @click="$emit('close')"
  >
    <ul class="ul flex flex-col justify-between">
      <li v-for="link in links" :key="link.label">
        <a @click="$emit('jump', link.href)">{{ link.label }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    links: {
      type: Array,
      default: () => [],
    },
    show: {
      type: Boolean,
      default: false,
    },
  },

  computed: {
    navClass() {
      return {
        show: this.show,
      }
    },
  },
}
</script>

<style lang="scss" scoped>
.nav-modal {
  position: fixed;
  height: 100%;
  width: 100%;
  z-index: 9000;
  background-color: rgba(255, 255, 255, 0.9);
  transition: all 0.5s;
  opacity: 0;
  pointer-events: none;

  &.show {
    opacity: 1;
    pointer-events: auto;
    transition: all 0.5s;
  }
  * {
    font-size: 30px;
  }
  a {
    cursor: pointer;
    text-decoration: none;
  }
}
.ul {
  height: 40%;
}
</style>
