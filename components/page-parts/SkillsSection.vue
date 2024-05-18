<template>
  <section>
    <div class="app-container">
      <h2 id="skills" class="section-title">Services Proposés</h2>
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
        <h3 class="h3 mb-2">autres</h3>
        <p class="experience mb-1">Expérience de travail à court terme  utilisation en dehors du travail</p>
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
          title: '•	Orthodontie',
          experience: '•	Appareils dentaires fixes et amovibles.',
          description:
            '•	Diagnostic et traitement des malocclusions dentaires.',
        },
        {
          title: '•	Implantologie',
          experience: '•	Remplacement des dents manquantes par des implants dentaires.',
          description:
            '•	Chirurgie implantaire avec techniques avancées.',
        },
        {
          title: '•	Chirurgie Orale et Maxillo-Faciale',
          experience: '•	Extraction des dents de sagesse.',
          description: '•	Traitement des fractures et anomalies de la mâchoire.',
        },
        {
          title: '•	Laser Dentaire',
          experience: '•	Traitements des maladies des gencives.',
          description:
            '•	Blanchiment des dents et autres interventions esthétiques.',
        },
        {
          title: '•	Esthétique Dentaire',
          experience: '•	Facettes dentaires.',
          description:
            '•	Blanchiment des dents.•	Remodelage des dents.',
        },   {
          title: '•	Esthétique Dentaire',
          experience: '•	Facettes dentaires.',
          description:
            '•	Blanchiment des dents.•	Remodelage des dents.',
        },

      ]
    },
    skillOthers() {
      return [
        '•	Esthétique ',
        '•	Laser Dentaire',

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
