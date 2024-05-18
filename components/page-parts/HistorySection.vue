<template>
  <section>
    <div class="app-container">
      <h2 id="history" class="section-title">Diplômes  et Qualifications</h2>
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
import HistoryCard from './HistoryCard.vue'

export default {
  components: {
    HistoryCard,
  },
  computed: {
    histories() {
      return [
        {
          title: '•	Diplôme Universitaire en Orthodontie',
          period: '2020',
          description:
            '•	Faculté de Médecine de Dijon, France',
          techStacks: [
            'France',
            'Dijon',
            'Médecine',

          ],
        },
        {
          title: '•	Diplôme d\'Université d\'Implantologie Chirurgicale Orale et Maxillo-Faciale',
          period: '2018/01〜2020/03',
          description:
            '•	Faculté de Médecine de Toulouse, France',
          techStacks: ['Médecine', 'Toulouse', 'France'],
        },
        {
          title: '•	Diplôme d\'Université en Laser et Médecine',
          period: '2016/12~2017/12',
          description:
            '•	Université de Bordeaux, France',
          techStacks: ['Bordeaux', 'France'],
        },
        {
          title: '•	Master en Esthétique Dentaire',
          period: '2011/04〜2017/03',
          description:
            '•	Université de Genève, Suisse',
          techStacks: ['Université', 'Genève', 'Suisse'],
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
