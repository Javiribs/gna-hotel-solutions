<script setup>
import logoFullWhite from '../assets/logos/logo-gnahs-white.png'
</script>

<template>
  <header class="header">
    <a href="#" class="header__brand">
      <img :src="logoFullWhite" alt="GNA Hotel Solutions">
    </a>

    <nav class="header__nav">
      <a href="#hotel">Hotel</a>
      <a href="#ofertas">Ofertas</a>
      <a href="#reservar" class="header__cta">Reservar</a>
    </nav>
  </header>
</template>