<template>
  <q-page padding>
    <h4 class="text-h4">Pretraživanje knjiga</h4>

    <p>Unesite podatak prema kojem želite pretražiti knjige.</p>

    <div class="row q-col-gutter-md">
      <div class="col-12 col-md-5">
        <q-input
          v-model="unos"
          label="Unesite naslov ili autora"
          outlined
        />
      </div>

      <div class="col-12 col-md-4">
        <q-select
          v-model="nacinPretrage"
          :options="opcije"
          label="Pretraži prema"
          outlined
          emit-value
          map-options
        />
      </div>

      <div class="col-12 col-md-3">
        <q-btn
          label="Traži"
          color="primary"
          @click="trazi"
        />
      </div>
    </div>

    <div v-if="pretrazeno" class="q-mt-lg">
      <h5 class="text-h5">Rezultati pretraživanja</h5>

      <q-table
        v-if="rezultati.length > 0"
        :rows="rezultati"
        :columns="columns"
        row-key="id"
      />

      <p v-else>Nema pronađenih knjiga.</p>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const unos = ref('')
const nacinPretrage = ref('naslov')
const pretrazeno = ref(false)
const rezultati = ref([])

const opcije = [
  { label: 'Naslov', value: 'naslov' },
  { label: 'Autor', value: 'autor' }
]

const columns = [
  {
    name: 'naslov',
    label: 'Naslov',
    field: 'naslov'
  },
  {
    name: 'autor',
    label: 'Autor',
    field: 'autor'
  },
  {
    name: 'godina',
    label: 'Godina izdanja',
    field: 'godina'
  },
  {
    name: 'zanr',
    label: 'Žanr',
    field: 'zanr'
  }
]

const knjige = [
  {
    id: 1,
    naslov: 'Zločin i kazna',
    autor: 'Fjodor Dostojevski',
    godina: 1866,
    zanr: 'Roman'
  },
  {
    id: 2,
    naslov: 'Mali princ',
    autor: 'Antoine de Saint-Exupéry',
    godina: 1943,
    zanr: 'Fantastika'
  },
  {
    id: 3,
    naslov: '1984.',
    autor: 'George Orwell',
    godina: 1949,
    zanr: 'Distopija'
  },
  {
    id: 4,
    naslov: 'Na Drini ćuprija',
    autor: 'Ivo Andrić',
    godina: 1945,
    zanr: 'Povijesni roman'
  }
]

function trazi() {
  pretrazeno.value = true

  const tekst = unos.value.toLowerCase().trim()

  rezultati.value = knjige.filter((knjiga) => {
    return knjiga[nacinPretrage.value]
      .toLowerCase()
      .includes(tekst)
  })
}
</script>