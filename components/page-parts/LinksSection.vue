<template>
  <section>
    <div class="app-container">
      <h2 id="links" class="section-title">Philosophie de Soins</h2>
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
          title: ' Dr. Mustapha ELMENDILI ',
          url: 'https://github.com/nek0meshi/shogi-board',
          description:
            'Le Dr. Mustapha ELMENDILI s\'engage à offrir des soins dentaires de haute qualité en utilisant les technologies les plus récentes et les meilleures pratiques dans le domaine de la dentisterie. Sa priorité est le bien-être de ses patients, en assurant des traitements personnalisés et adaptés à chaque cas particulier.',
          techStacks: ['Mustapha', 'ELMENDILI'],
          fileName: 'shogi.jpg',
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
