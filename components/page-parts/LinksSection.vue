<template>
  <section>
    <div class="app-container">
      <h2 id="links" class="section-title">LINKS</h2>
      <ul class="flex flex-row flex-wrap justify-between">
        <LinkCard
          v-for="link in links"
          :key="link.title"
          :title="link.title"
          :url="link.url"
          :description="link.description"
          :tech-stacks="link.techStacks"
          :file-name="link.fileName"
          class="link-card"
        />
      </ul>
    </div>
  </section>
</template>

<script>
import LinkCard from './LinkCard.vue'

export default {
  components: {
    LinkCard,
  },
  computed: {
    links() {
      return [
        {
          title: '将棋盤',
          url: 'https://github.com/nek0meshi/shogi-board',
          description:
            '将棋盤を製作。駒を動かしたり、相手の駒を取ったり、成ったりすることができる。' +
            'TypeScriptやVue3のの学習も兼ねて製作。',
          techStacks: ['Vue.js3', 'TypeScript'],
          fileName: 'shogi.jpg',
        },
        {
          title: 'Profile',
          url: 'https://github.com/nek0meshi/profile',
          description:
            '本サイト。エンジニアとしてのスキル・経歴・リンク集の紹介や、HTML/CSSの学習のため製作。',
          techStacks: ['HTML/CSS', 'Nuxt.js', 'SCSS'],
          fileName: 'profile.jpg',
        },
        {
          title: 'Tetris',
          url: 'https://github.com/nek0meshi/tetris',
          description: 'テトリスゲーム。TypeScript・Reactの学習のため製作。',
          techStacks: ['TypeScript', 'React'],
          fileName: 'tetris.jpg',
        },
        {
          title: 'TODOリスト',
          url: 'https://github.com/nek0meshi/todo-list',
          description: '単純なTODOリスト。Go言語の学習のため製作。',
          techStacks: ['Golang', 'Vue.js3', 'Bulma'],
          fileName: 'todo-list.jpg',
        },
        {
          title: 'タイピングゲーム',
          url: 'https://github.com/nek0meshi/typing',
          description:
            '単純なタイピングゲーム。TypeScript・Vue.js3の学習のため製作。',
          techStacks: ['Vue.js3', 'TypeScript'],
          fileName: 'typing.jpg',
        },
        {
          title: 'ブログ',
          url: 'https://yushi-dev.hatenablog.com/',
          description:
            '現職の入社後に始めたブログ。学習の記録としての記事が多く、イベント観覧や読んだ書籍に関する記事もある。はてなブログ。2020/06〜現在。',
          fileName: 'hatenablog-logotype.svg',
        },
        {
          title: 'Profile v1',
          url: 'https://github.com/nek0meshi/profile/tree/master/v1',
          description:
            'プロフィールページの過去バージョン。エンジニアとしてのスキル・経歴・リンク集の紹介や、HTML/CSSの学習のため製作。',
          techStacks: ['HTML/CSS', 'Nuxt.js', 'SCSS', 'bulma'],
          fileName: 'profile-v1.jpg',
        },
      ]
    },
  },
}
</script>

<style lang="scss" scoped>
section {
  background-color: $bg-1;
}
.link-card {
  width: calc(50% - 15px);
  margin-bottom: 50px;

  @media (max-width: $tablet-max-width) {
    width: 100%;
  }
}
</style>
