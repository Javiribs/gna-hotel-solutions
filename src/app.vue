<script setup>
import { ref } from 'vue'

import Header from './components/header.vue'
import Hero from './components/hero.vue'
import About from './components/about.vue'
import Filter from './components/filter.vue'
import Features from './components/features.vue'
import Footer from './components/footer.vue'

const activeFilter = ref('todos')
</script>

<template>
  <Header />
  <Hero />
  <About />
  <Filter v-model="activeFilter" />
  <Features :active-filter="activeFilter" />
  <Footer />
</template>