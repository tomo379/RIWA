<template>
  <q-page padding>
    <h4 class="text-h4">Popis svih knjiga</h4>

    <p>
      Ovdje možete pogledati popis knjiga koje se nalaze u našoj knjižnici.
    </p>

    <q-table
      title="Knjige"
      :rows="rows"
      :columns="columns"
      row-key="id"
    />
  </q-page>
</template>

<script setup>
const columns = [
  {
    name: 'naslov',
    label: 'Naslov',
    field: 'naslov',
    style: 'width: 30%',
    headerStyle: 'font-weight: bold'
  },
  {
    name: 'autor',
    label: 'Autor',
    field: 'autor',
    style: 'width: 25%',
    headerStyle: 'font-weight: bold'
  },
  {
    name: 'godina',
    label: 'Godina izdanja',
    field: 'godina',
    style: 'width: 20%',
    headerStyle: 'font-weight: bold'
  },
  {
    name: 'zanr',
    label: 'Žanr',
    field: 'zanr',
    style: 'width: 25%',
    headerStyle: 'font-weight: bold'
  }
]

const rows = [
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
</script>