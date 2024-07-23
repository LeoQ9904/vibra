<script setup>
import HeaderComponent from './components/HeaderComponent.vue'
import FooterComponent from './components/FooterComponent.vue'
import ArtistComponent from './components/ArtistComponent.vue'

import { usePrincipalStore } from './stores/principal'

const principalStore = usePrincipalStore()

principalStore.getArtistas()

const artistas = principalStore.artistas
</script>
<template>
  <HeaderComponent />
  <div class="flex flex-col min-h-screen bg-[#400073] text-[#D0A5F9]">
    <main class="mt-10">
      <div class="flex py-10 justify-center">
        <div class="flex-1 max-w-md">
          <input
            class="flex h-10 border border-input px-3 py-2 text-sm ring-offset-background file:border-0 file:bg-transparent file:text-sm file:font-medium placeholder:text-muted-foreground focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:cursor-not-allowed disabled:opacity-50 w-full rounded-full bg-white focus:ring-2 focus:ring-[#D3F474] focus:border-[#D3F474]"
            type="search"
            placeholder="Buscar artista..."
          />
        </div>
      </div>
      <div
        class="max-w-6xl mx-auto grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8 px-4 md:px-6"
      >
        <template v-for="(artista, index) in artistas" :key="index">
          <ArtistComponent :name="artista.name" :avatar="artista.images[0].url" />
        </template>
      </div>
    </main>
    <FooterComponent />
  </div>
</template>
