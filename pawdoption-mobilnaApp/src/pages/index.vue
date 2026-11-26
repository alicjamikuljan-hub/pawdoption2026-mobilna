<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title> Pawdoption aplikacija </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> Essential Links </q-item-label>

        <EssentialLink
          v-for="link in linksList"
          :key="link.label"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import EssentialLink from '@/components/EssentialLink.vue'

const linksList = [
  {
    label: 'Početna',
    caption: 'Početna stranica',
    icon: 'school',
    link: '/'
  },
  {
    label: 'Prijava',
    caption: 'Prijava korisnika',
    icon: 'code',
    link: '/prijava'
  },
  {
    label: 'Registracija',
    caption: 'Registracija korisnika',
    icon: 'chat',
    link: '/registracija'
  },
  {
    label: 'Moja opažanja',
    caption: 'Moja opažanja',
    icon: 'record_voice_over',
    link: '/opazanja'
  },
  {
    label: 'Detalji životinje',
    caption: 'Podaci o životinji',
    icon: 'pets',
    link: '/zivotinja/1'
  },
  {
    label: 'Zahtjev za udomljavanje',
    caption: 'Slanje zahtjeva',
    icon: 'favorite',
    link: '/zahtjev-za-udomljavanje'
  },
  {
    label: 'O nama / Sklonište',
    caption: 'Informacije o skloništu',
    icon: 'info',
    link: '/o-nama'
  },
  {
    label: 'Profil',
    caption: 'Profil korisnika',
    icon: 'person',
    link: '/profil'
  }
]

const leftDrawerOpen = ref(false)

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>