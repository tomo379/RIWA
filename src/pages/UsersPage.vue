<template>
  <q-page padding>
    <div class="q-pa-md q-gutter-sm">
      <q-btn color="primary" icon="mail" label="On Left" />

      <q-btn color="secondary" icon-right="mail" label="On Right" />

      <q-btn
        color="red"
        icon="mail"
        icon-right="send"
        label="On Left and Right"
      />

      <br />

      <q-btn icon="phone" label="Stacked" stack glossy color="purple" />

      <br />

      <q-btn
        color="green"
        icon="person"
        label="Klikni me"
        @click="prikaziPoruku"
      />
    </div>
  </q-page>
</template>

<script setup>
function prikaziPoruku() {
  alert('Gumb je kliknut');
}
</script>
