<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="bg-grey-9 text-white">
      <q-toolbar>
        <q-btn flat dense round icon="menu" @click="drawer = !drawer" />
        <q-toolbar-title>Pawdoption</q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="drawer" show-if-above bordered>
      <q-list>
        <q-item v-for="item in menu" :key="item.to"
                clickable :to="item.to" exact>
          <q-item-section>{{ item.label }}</q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue';

const drawer = ref(false);

const menu = [
  { label: 'Početna', to: '/' },
  { label: 'Prijava', to: '/prijava' },
  { label: 'Registracija', to: '/registracija' },
  { label: 'Životinje za udomljavanje', to: '/zivotinje-za-udomljavanje' },
  { label: 'Detalji životinje', to: '/zivotinja/1' },
  { label: 'Zahtjev za udomljavanje', to: '/zahtjev-za-udomljavanje' },
  { label: 'O nama / Sklonište', to: '/o-nama' },
  { label: 'Profil', to: '/profil' }
];
</script>