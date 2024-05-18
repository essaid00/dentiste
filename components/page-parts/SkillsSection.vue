<template>
  <section>
    <div class="app-container">
      <h2 id="skills" class="section-title">SKILLS</h2>
      <ul class="flex flex-wrap justify-between">
        <SkillCard
          v-for="skill in skills"
          :key="skill.title"
          :title="skill.title"
          :experience="skill.experience"
          :description="skill.description"
          class="skill-card skill-card-fade-in"
        />
      </ul>
      <div class="skill-others-card skill-card-fade-in">
        <h3 class="h3 mb-2">その他</h3>
        <p class="experience mb-1">短期間の実務経験や実務外での利用</p>
        <p>{{ skillOthers.join(', ') }}</p>
      </div>
    </div>
  </section>
</template>

<script>
import SkillCard from './SkillCard'

export default {
  components: {
    SkillCard,
  },

  computed: {
    skills() {
      return [
        {
          title: 'PHP',
          experience: '実務5年',
          description:
            'サーバサイドではPHPを使う機会が多い。Laravelを中心に、CakePHP2も経験がある。',
        },
        {
          title: 'JavaScript',
          experience: '実務4年',
          description:
            'Vue.js・jQueryを使うケースが多い。既存システムへのwebpackやTypeScriptの導入も担当。',
        },
        {
          title: 'iOS/swift',
          experience: '実務1年',
          description: '受託開発にて、業務システムの制作などで利用。',
        },
        {
          title: 'HTML/CSS',
          experience: '実務半年/実務外半年',
          description:
            '実務で使うケースは少なく、本ページは学習も兼ねて作成した。',
        },
        {
          title: 'Python',
          experience: '実務3ヶ月/実務外2年',
          description:
            '主に、学生時代の研究活動で利用した。numpy/pandas等を利用した統計解析や、簡単なシステム操作のUI作成など。',
        },
        {
          title: '資格など',
          experience: '-',
          description:
            '基本情報技術者試験, 応用情報技術者, TOEIC 770点, 給与計算実務能力検定 2級',
        },
      ]
    },
    skillOthers() {
      return [
        'DB設計',
        'SQL',
        'Java',
        'C++',
        'C#',
        'Objective-C',
        'Go',
        'TypeScript',
        'React',
        'AngularJS',
        'Nuxt.js',
        'Next.js',
        'SCSS',
        'AWS',
        'Line Messaging API',
        'Docker',
        'Vagrant',
      ]
    },
  },

  mounted() {
    // 要素の位置までスクロールしたらフェードインする.
    const element = document.querySelectorAll('.skill-card-fade-in')
    const windowH = window.innerHeight

    window.addEventListener('scroll', () => {
      // 係数
      const k = 1.1

      for (const e of element) {
        if (windowH > e.getBoundingClientRect().top * k) {
          e.classList.add('show')
        } else {
          e.classList.remove('show')
        }
      }
    })
  },
}
</script>

<style lang="scss" scoped>
@keyframes fadein {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
.skill-card {
  width: calc(33% - 10px);

  @media (max-width: $tablet-max-width) {
    width: calc(50% - 15px);
  }
  @media (max-width: $mobile-max-width) {
    width: 100%;
  }
}
.skill-others-card {
  padding: 10px 20px;
  border: solid 1px $gray-3;
  border-radius: 10px;
  .experience {
    font-size: 14px;
    font-weight: bold;
  }
}
.skill-card-fade-in {
  opacity: 0;
  &.show {
    animation: fadein 0.5s 0.1s ease-in forwards;
  }
}
</style>
