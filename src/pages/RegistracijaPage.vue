<template>
  <q-page padding>
    <h4 class="text-h4">Registracija korisnika</h4>

    <p>Unesite podatke za izradu korisničkog računa.</p>

    <div style="max-width: 400px">
      <q-input
        v-model="ime"
        label="Ime"
        outlined
        class="q-mb-md"
      />

      <q-input
        v-model="prezime"
        label="Prezime"
        outlined
        class="q-mb-md"
      />

      <q-input
        v-model="korisnickoIme"
        label="Korisničko ime"
        outlined
        class="q-mb-md"
      />

      <q-input
        v-model="email"
        label="E-mail"
        type="email"
        outlined
        class="q-mb-md"
      />

      <q-input
        v-model="lozinka"
        label="Lozinka"
        type="password"
        outlined
        class="q-mb-md"
      />

      <q-btn
        label="Potvrdi"
        color="primary"
        @click="registracija"
      />

      <p v-if="poruka" class="q-mt-md">
        {{ poruka }}
      </p>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const ime = ref('')
const prezime = ref('')
const korisnickoIme = ref('')
const email = ref('')
const lozinka = ref('')
const poruka = ref('')

function registracija() {
  if (
    ime.value === '' ||
    prezime.value === '' ||
    korisnickoIme.value === '' ||
    email.value === '' ||
    lozinka.value === ''
  ) {
    poruka.value = 'Molimo ispunite sva polja.'
  } else {
    poruka.value = 'Podaci su uspješno uneseni.'
  }
}
</script>
