<template>
  <q-page class="q-pa-md">
    <h1 class="text-h5">Početna</h1>
    <p>Dobrodošli na Pawdoption aplikaciju.</p>
    <p>Ovdje možete udomiti životinje iz raznih azila.</p>
    <q-btn label="Životinje" to="/zivotinje-za-udomljavanje" color="grey-9" />
    <p>ID zivotinje-za-udomljavanje: {{ route.params.id }}</p>
    </q-page>
 
</template>


<script setup>
import { useRoute } from 'vue-router';
const route = useRoute();
</script>



<style lang="sass" scoped>
.my-card
  width: 100%
</style>