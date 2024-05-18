<template>
  <section>
    <div class="app-container">
      <h2 id="history" class="section-title">HISTORY</h2>
      <ul class="flex flex-col mx-auto history-card-list">
        <history-card
          v-for="history in histories"
          :key="history.title"
          :title="history.title"
          :period="history.period"
          :description="history.description"
          :tech-stacks="history.techStacks"
          class="history-card"
        />
      </ul>
    </div>
  </section>
</template>

<script>
import HistoryCard from './HistoryCard'

export default {
  components: {
    HistoryCard,
  },
  computed: {
    histories() {
      return [
        {
          title: '株式会社スマレジ',
          period: '2020/04〜現在',
          description:
            'Webエンジニアとして、勤怠管理の自社サービスの開発に携わっている。' +
            'リードエンジニアとして、重要度の高い実装や上流寄りの工程、教育やレビューを担当。' +
            '1on1の開始、振り返り会の企画・進行などといったチーム運営にも取り組んでいる。',
          techStacks: [
            'Laravel',
            'Vue.js',
            'CakePHP2',
            'jQuery',
            'TypeScript',
            'SCSS',
          ],
        },
        {
          title: '株式会社SICデジタル',
          period: '2018/01〜2020/03',
          description:
            'Webアプリ開発やiOSアプリ開発を担当。' +
            '1~10人月程度の小規模な新規開発・改修に携わった。',
          techStacks: ['Laravel', 'Vue.js', 'iOS/swift', 'Objective-C'],
        },
        {
          title: '株式会社Silett',
          period: '2016/12~2017/12',
          description:
            '研究室の同期の起業に参加した。' +
            '自社制作の対話システムを活用したアプリケーション制作に携わった。' +
            'スマホアプリのクライアント部、サーバ部、インフラ周りなどを担当した。',
          techStacks: ['iOS/swift', 'PHP', 'C#', 'AWS', 'Line Messaging API'],
        },
        {
          title: '大阪大学・大阪大学大学院',
          period: '2011/04〜2017/03',
          description:
            '研究室では、コミュニケーションロボットに関する研究に携わった。' +
            'Pythonを利用し、心拍データの加工・計算や、統計解析などを行った。' +
            'Java・C++を利用し、コミュニケーションロボットの挙動を制御するシステムを制作した。',
          techStacks: ['Python', 'Java', 'C++'],
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
</style>
