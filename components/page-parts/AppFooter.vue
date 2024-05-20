<template>
  <footer>
    <ul class="logos flex flex-row">
      <li v-for="link in links" :key="link.title">
        <a :href="link.url" target="_blank">
          <img
            :src="'logo/' + link.imageFileName"
            class="link-logo"
            :style="{ 'background-color': link.bdColor || '#fff' }"
          />
        </a>
      </li>
    </ul>
    <p>©︎ 2023-2024 Dr. Mustapha ELMENDILI</p>
  </footer>
</template>

<script>
export default {
  computed: {
    links() {
      return [
        {
          title: 'FaceBook',
          url: 'https://web.facebook.com/mustapha.elmendili/?',
          imageFileName: 'facebook.ico',
          bdColor: '#000',
        },
        {
          title: 'linkedin',
          url: 'https://ma.linkedin.com/in/mustapha-el-mendili-517889104&ved=2ahUKEwiq5s-W9pmGAxUVR_EDHcRjBJIQFnoECBkQAQ&usg=AOvVaw3YBPIwClXls17X-iZt74oF',
          imageFileName: 'linkedin.webp',
        },
        {
          title: 'twitter',
          url: 'https://x.com/drelmendili_mus?lang=fr&mx=2',
          imageFileName: 'Twitter.png',
        },
      ]
    },
  },
}
</script>

<style lang="scss" scoped>
* {
  color: #fff;
}

footer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 20px;
  height: 180px;
  width: 100%;
  background-color: $main-1;
}

.logos {
  gap: 30px;
}

.link-logo {
  background-color: #fff;
  height: 50px;
  width: 50px;
  border-radius: 100%;
  transition: 0.5s;
  &:hover {
    transition: 0.5s;
    transform: translateY(-5px);
  }
}
</style>
