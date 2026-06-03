<script setup>
import logoFooter from '../assets/logos/logo-gnahs.png'
</script>

<template>
  <footer class="footer">
    <div class="footer__inner">
      <div class="footer__brand">
        <img :src="logoFooter" alt="GNA Hotel Solutions">
      </div>

      <div class="footer__links">
        <nav class="footer__column">
          <a href="#">Contacte</a>
          <a href="#">Newsletter</a>
          <a href="#">Treballa amb nosaltres</a>
        </nav>

        <nav class="footer__column">
          <a href="#">Política de cookies</a>
          <a href="#">Política de privacitat</a>
          <a href="#">Avís legal</a>
        </nav>

        <p class="footer__credit">
          Desenvolupat per <span>GNA Hotel Solutions</span>
        </p>
      </div>
    </div>
  </footer>
</template>