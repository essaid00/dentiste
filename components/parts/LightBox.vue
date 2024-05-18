<template>
  <transition name="fade">
    <div
      v-show="filePath"
      class="light-box flex flex-row justify-around items-center"
      @click="$emit('close')"
    >
      <button
        class="arrow-button left-arrow"
        :class="{ hasNext: hasLeft }"
        @click.stop="$emit('go-left')"
      />
      <img class="image" :src="filePath" @click.stop />
      <button
        class="arrow-button right-arrow"
        :class="{ hasNext: hasRight }"
        @click.stop="$emit('go-right')"
      />
    </div>
  </transition>
</template>

<script>
export default {
  props: {
    filePath: {
      type: String,
      default: '',
    },
    hasLeft: {
      type: Boolean,
      default: false,
    },
    hasRight: {
      type: Boolean,
      default: false,
    },
  },
}
</script>

<style lang="scss" scoped>
.light-box {
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 10000;
  background-color: #000;
  cursor: pointer;
}
.image {
  max-width: calc(100% - 150px);
  max-height: 90%;
  object-fit: contain;

  @media (max-width: $mobile-max-width) {
    max-width: 100%;
  }
}
$arrow-color: #aaa;
$arrow-size: 15px;
$arrow-btn-size: 50px;
.arrow-button {
  position: relative;
  background-color: #333;
  width: $arrow-btn-size;
  height: $arrow-btn-size;
  border-radius: 50%;
  opacity: 0;

  &::after {
    content: '';
    position: absolute;
    top: calc($arrow-btn-size / 2 - $arrow-size);
    border-top: $arrow-size solid transparent;
    border-bottom: $arrow-size solid transparent;
  }
  &.left-arrow::after {
    border-right: $arrow-size solid $arrow-color;
    left: calc($arrow-btn-size / 2 - $arrow-size * 2 / 3);
  }
  &.right-arrow::after {
    border-left: $arrow-size solid $arrow-color;
    right: calc($arrow-btn-size / 2 - $arrow-size * 2 / 3);
  }

  &.hasNext {
    opacity: 0.5;
  }

  @media (max-width: $mobile-max-width) {
    position: fixed;
    top: 0;
    width: 100px;
    height: 100%;
    border-radius: 0;

    &::after {
      display: none;
    }

    &.left-arrow {
      left: 0;
    }

    &.right-arrow {
      right: 0;
    }

    &.hasNext {
      opacity: 0;
    }
  }
}
.fade-enter-active {
  transition: all 0.5s ease;
}
.fade-leave-active {
  transition: all 0.5s ease;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
