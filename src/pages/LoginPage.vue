<template>
  <q-page padding>
    <h4 class="text-h4">Prijava korisnika</h4>

    <p>Unesite svoje korisničko ime i lozinku za prijavu.</p>

    <div style="max-width: 400px">
      <q-input
        v-model="korisnickoIme"
        label="Korisničko ime"
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
        @click="prijava"
      />

      <p v-if="poruka" class="q-mt-md">
        {{ poruka }}
      </p>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const korisnickoIme = ref('')
const lozinka = ref('')
const poruka = ref('')

function prijava() {
  if (korisnickoIme.value === '' || lozinka.value === '') {
    poruka.value = 'Molimo unesite korisničko ime i lozinku.'
  } else {
    poruka.value = 'Podaci su uneseni.'
  }
}
</script>
