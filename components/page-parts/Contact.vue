<template>
   <section id="contact">
    <div class="app-container">
      <h2 id="photos" class="section-title">CONTACT</h2>
       <div class="flex flex-row flex-wrap justify-between">
        <div class="photo-card m-2">
          <h2>
            Pour toute consultation ou prise de rendez-vous,
            n'hésitez pas à contacter le Dr. Mustapha ELMENDILI aux coordonnées ci-dessus.
          </h2>
  <h2 class="pb-4 mt-2">
          <span class="text-green-700">Adresse  :</span>
          <span class="green--text"> Route de Kénitra, Résidence Elmdaghri, Imm. B, Appt. 3,
10010, Salé, Maroc
</span>
        </h2>
        <div class="py-4 subheading font-weight-bold">
          <v-icon large color="green" left>Contact :</v-icon>
          <span class="text-green-700">•	Téléphone :&nbsp;</span>
          <span class="green--text">Fix :+212 537 78 54 62</span>

        </div>
        <div class="py-4 subheading font-weight-bold">
          <v-icon large color="green" left>fas fa-check</v-icon>
          <span class="text-green-700">Fax :</span>
          <span class="green--text">+212 537 84 40 70</span>
        </div>
        <div class="py-4 subheading font-weight-bold">
          <v-icon large color="green" left>E-contact</v-icon>
          <span class="text-green-700">Email :</span>
          <span class="green--text">mustatpha@gmail.com</span>
        </div>
        <div class="py-4 subheading font-weight-bold">
          <v-icon large color="green" left>fas fa-phone</v-icon>
          <span class="text-green-700">Site :&nbsp;</span>
          <span class="green--text">https://obliged-virgie-fhapplication-dede0317.koyeb.app</span>
        </div>

      </div>
<div class="photo-card">
     <form @submit.prevent="submit">
    <v-text-field
      v-model="name.value.value"
      :counter="10"
      :error-messages="name.errorMessage.value"
      label="Nom et Prénom"
    ></v-text-field>

    <v-text-field
      v-model="phone.value.value"
      :counter="7"
      :error-messages="phone.errorMessage.value"
      label="Numéro de téléphone"
    ></v-text-field>

    <v-text-field
      v-model="email.value.value"
      :error-messages="email.errorMessage.value"
      label="E-mail"
    ></v-text-field>

    <v-select
      v-model="select.value.value"
      :error-messages="select.errorMessage.value"
      :items="items"
      label="choisir"
    ></v-select>



    <v-btn
      class="me-4 white--text bg-slate-500 bg-slate-300"
      large flat
      color="green"

      type="submit"
    >
      Envoyer un message
    </v-btn>

    <v-btn class="bg-red-200"  @click="handleReset">
      vider
    </v-btn>
  </form>
</div>

      </div>
      <div>
<iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d4586.003177534808!2d-6.818669173297126!3d34.04807482040804!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0xda76bc9ca372ecb%3A0x60228ebcd081d59c!2sEL%20MENDILI%20MUSTAPHA%20(Orthodontiste)!5e0!3m2!1sfr!2sma!4v1716192044535!5m2!1sfr!2sma"
 width="100%" height="450"
 style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
</div>
    </div>

    </section>

</template>
<script setup>
  import { ref } from 'vue'
  import { useField, useForm } from 'vee-validate'

  const { handleSubmit, handleReset } = useForm({
    validationSchema: {
      name (value) {
        if (value?.length >= 2) return true

        return 'Name needs to be at least 2 characters.'
      },
      phone (value) {
        if (value?.length > 9 && /[0-9-]+/.test(value)) return true

        return 'Phone number needs to be at least 9 digits.'
      },
      email (value) {
        if (/^[a-z.-]+@[a-z.-]+\.[a-z]+$/i.test(value)) return true

        return 'Must be a valid e-mail.'
      },
      select (value) {
        if (value) return true

        return 'Select an item.'
      },
      checkbox (value) {
        if (value === '1') return true

        return 'Must be checked.'
      },
    },
  })
  const name = useField('name')
  const phone = useField('phone')
  const email = useField('email')
  const select = useField('select')
  const checkbox = useField('checkbox')

  const items = ref([
    'proposition',
    'message perso',
    'lettre',
    'sugjestion',
  ])

  const submit = handleSubmit(values => {
    alert(JSON.stringify(values, null, 2))
  })
</script>

<style lang="scss" scoped>

.photo-card {
  width: calc(45% - 5px);
  margin-bottom: 30px;
  cursor: pointer;
  transition: 0.2s;

  &:hover {
    filter: brightness(80%);
  }

  @media (max-width: $tablet-max-width) {
    width: calc(50% - 5px);
  }

  @media (max-width: $mobile-max-width) {
    width: 100%;
  }
}
</style>
