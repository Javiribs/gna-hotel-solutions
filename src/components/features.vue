<script setup>
import { computed } from 'vue'
import { offers } from '../data/offers'

const props = defineProps({
  activeFilter: {
    type: String,
    default: 'todos'
  }
})

const visibleOffers = computed(() => {
  if (props.activeFilter === 'todos') return offers

  return offers.filter((offer) =>
    offer.tags.includes(props.activeFilter)
  )
})

const tagLabels = {
  tecnologia: 'Tecnologia',
  marketing: 'Màrqueting'
}
</script>

<template>
  <section class="features" id="ofertas">
    <div class="features__inner container">
      <article
        v-for="offer in visibleOffers"
        :key="offer.id"
        class="feature-card"
        :class="{ 'feature-card--reverse': offer.reverse }"
      >
        <img
          v-if="!offer.reverse"
          class="feature-card__image"
          :src="offer.image"
          :alt="offer.title"
        >

        <div class="feature-card__content">
          <div class="feature-card__tags">
            <span
              v-for="tag in offer.tags"
              :key="tag"
              class="feature-card__tag"
            >
              {{ tagLabels[tag] }}
            </span>
          </div>

          <h3>{{ offer.title }}</h3>
          <p>{{ offer.text }}</p>
          <a :href="offer.link">Més informació</a>
        </div>

        <img
          v-if="offer.reverse"
          class="feature-card__image"
          :src="offer.image"
          :alt="offer.title"
        >
      </article>
    </div>  
  </section>
</template>