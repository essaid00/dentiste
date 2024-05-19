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
          url: 'https://obliged-virgie-fhapplication-dede0317.koyeb.app',
          description:
            'Le Dr. Mustapha ELMENDILI s\'engage à offrir des soins dentaires de haute qualité en utilisant les technologies les plus récentes et les meilleures pratiques dans le domaine de la dentisterie. Sa priorité est le bien-être de ses patients, en assurant des traitements personnalisés et adaptés à chaque cas particulier.',
          techStacks: ['Mustapha', 'ELMENDILI'],
          fileName: 'lesdentes.jpg',
        },
        {
          title: ' Affiliations professionnelles',
          url: 'https://obliged-virgie-fhapplication-dede0317.koyeb.app',
          description:
           'Affiliations professionnelles'
            ,
          techStacks: ['• Membre de l\'Ordre National des Médecins Dentistes du Maroc',
            '• Membre de la Société Marocaine d\'Orthodontie',
            '• Membre de la Société Française d\'Implantologie Orale et Maxillo-Faciale',
            '• Membre de la Société Internationale de Laser Dentaire',
            '• Membre de l\'Académie Internationale d\'Esthétique Dentaire',],
          fileName: 'revealing-shot-stomatologist-chair-with-nobody.jpg',
        },
        {
          title: ' Certifications et récompenses',
          url: 'https://obliged-virgie-fhapplication-dede0317.koyeb.app',
          description:
           'Certifications et récompenses'
            ,
          techStacks: ['Certification en Invisalign, Align Technology, Inc.',
            'Certification en CEREC, Sirona Dental Systems',
            '• Lauréat du Prix de la Meilleure Présentation Clinique, Congrès de la Société Marocaine d\'Orthodontie (2015)',
            '• Membre de la Société Internationale de Laser Dentaire',
            '• Membre de l\'Académie Internationale d\'Esthétique Dentaire',],
          fileName: '1.jpg',
        },
        {
          title: ' Publications et présentations',
          url: 'https://obliged-virgie-fhapplication-dede0317.koyeb.app',
          description:
           'Auteur et co-auteur de plusieurs articles scientifiques dans des revues internationales de dentisterie'
            ,
          techStacks: ['Présentateur et conférencier lors de congrès et séminaires nationaux et internationaux sur l\'orthodontie, l\'implantologie, le laser dentaire et l\'esthétique dentaire',],
          fileName: 'dentist.jpg',
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
