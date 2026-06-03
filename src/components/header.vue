<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

import logoWhite from '../assets/logos/logo-gnahs-white.png'
import logoFullWhite from '../assets/logos/logo-gnahs-full-white.png'

const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 40
}

onMounted(() => {
  handleScroll()
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header class="header" :class="{ 'header--scrolled': isScrolled }">
    <a href="#" class="header__brand">
      <img
        :src="isScrolled ? logoFullWhite : logoWhite"
        alt="GNA Hotel Solutions"
      >
    </a>

    <nav class="header__nav">
      <a href="#hotel">Hotel</a>
      <a href="#ofertas">Ofertas</a>
      <a href="#reservar" class="header__cta">Reservar</a>
    </nav>
  </header>
</template>