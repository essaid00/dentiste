<template>
  <header class="header fixed w-full" :class="headerClass">
    <div class="header-wrap mx-auto text-white relative">
      <ul
        class="flex flex-row gap-4 justify-end items-center header-content header-links"
      >
        <li v-for="link in links" :key="link.label">
          <a class="header-link-a text-white" @click="scrollLink(link.href)">{{
            link.label
          }}</a>
        </li>
      </ul>
      <nav
        class="flex flex-row justify-end items-center header-content hamburger-wrap"
        :class="hamburgerWrapClass"
      >
        <a class="hamburger" @click="clickHamburger">
          <span class="hamburger-bar"></span>
          <span class="hamburger-bar"></span>
          <span class="hamburger-bar"></span>
        </a>
      </nav>
    </div>
    <NavModal
      :show="showNavModal"
      :links="links"
      @close="showNavModal = false"
      @jump="scrollLink($event)"
    />
  </header>
</template>

<script>
import NavModal from './NavModal.vue'

export default {
  components: {
    NavModal,
  },

  data() {
    return {
      showNavModal: false,
      isScrolled: false,
    }
  },

  computed: {
    links() {
      return [
        {
          href: '#about',
          label: 'ABOUT',
        },
        {
          href: '#history',
          label: 'HISTORY',
        },
        {
          href: '#skills',
          label: 'SKILLS',
        },
        {
          href: '#links',
          label: 'LINKS',
        },
        {
          href: '#photos',
          label: 'PHOTOS',
        },
      ]
    },
    headerClass() {
      return {
        scrolled: this.isScrolled,
      }
    },
    hamburgerWrapClass() {
      return {
        'show-modal': this.showNavModal,
      }
    },
  },

  mounted() {
    window.addEventListener('scroll', () => {
      const header = document.querySelector('.hero-image')
      this.isScrolled = window.scrollY > header.clientHeight - 50
    })
  },

  methods: {
    clickHamburger() {
      this.showNavModal = !this.showNavModal
    },
    scrollLink(href) {
      // https://www.fenet.jp/dotnet/column/language/javascript/7491#JavaScript
      const target = document.querySelector(href)
      const top = target.offsetTop - 80
      window.scrollTo({
        top,
        behavior: 'smooth',
      })
    },
  },
}
</script>

<style lang="scss" scoped>
.header {
  z-index: 8000;
  .header-wrap {
    & > * {
      transition: 1s;
    }
  }
  &.scrolled {
    .header-wrap {
      & > * {
        background-color: $main-1;
      }
    }
  }
}
.header-content {
  position: absolute;
  width: 100%;
  padding-left: 30px;
  padding-right: 30px;
  height: 56px;

  a {
    cursor: pointer;
  }
}
.header-links {
  @media (max-width: $mobile-max-width) {
    display: none;
  }
}
.header-link-a {
  display: block;
  position: relative;
  text-decoration: none;

  &::after {
    content: '';
    position: absolute;
    left: 0;
    bottom: -3px;
    width: 0;
    border-bottom: solid 2px $white;
    transition: 0.5s;
  }

  &:hover {
    &::after {
      transition: 0.5s;
      width: 100%;
    }
  }
}
.hamburger-bar {
  position: absolute;
  width: 30px;
  height: 2px;
  background-color: #eee;
  transition: 0.5s;

  &:nth-child(1) {
    top: calc(50% - 10px);
  }
  &:nth-child(2) {
    top: 50%;
  }
  &:nth-child(3) {
    top: calc(50% + 10px);
  }
}
.hamburger {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  position: relative;
  height: 24px;
  width: 24px;
  z-index: 10000;
}
.hamburger-wrap {
  display: none;
  @media (max-width: $mobile-max-width) {
    display: flex;
  }

  &.show-modal {
    .hamburger-bar {
      background-color: #000;
      transform: rotateZ(45deg);
      transition: 0.5s;
      &:nth-child(1) {
        top: 50%;
      }
      &:nth-child(2) {
        top: 50%;
      }
      &:nth-child(3) {
        top: 50%;
        transform: rotateZ(-45deg);
      }
    }
  }
}
</style>
