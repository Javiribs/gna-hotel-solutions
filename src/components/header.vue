<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

import logoWhite from '../assets/logos/logo-gnahs-white.png'
import logoFullWhite from '../assets/logos/logo-gnahs-full-white.png'

const isScrolled = ref(false)
const mobileMenuOpen = ref(false)

const toggleMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

const closeMenu = () => {
  mobileMenuOpen.value = false
}

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
  <header class="header" :class="{ 'header--scrolled': isScrolled || mobileMenuOpen }">
    <a href="#" class="header__brand" @click="closeMenu">
      <img
        :src="isScrolled || mobileMenuOpen ? logoFullWhite : logoWhite"
        alt="GNA Hotel Solutions"
      >
    </a>

    <nav class="header__nav">
      <a href="#hotel">Hotel</a>
      <a href="#ofertas">Ofertas</a>
      <a href="#reservar" class="header__cta">Reservar</a>
    </nav>

    <button
      class="header__hamburger"
      :class="{ 'header__hamburger--open': mobileMenuOpen }"
      type="button"
      aria-label="Abrir menú"
      @click="toggleMenu"
    >
      <span></span>
      <span></span>
      <span></span>
    </button>

    <div
      class="mobile-menu"
      :class="{ 'mobile-menu--open': mobileMenuOpen }"
    >
      <a href="#hotel" @click="closeMenu">Hotel</a>
      <a href="#ofertas" @click="closeMenu">Ofertas</a>
      <a href="#reservar" @click="closeMenu">Reservar</a>
    </div>
  </header>
</template>