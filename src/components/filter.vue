<script setup>
defineProps({
  modelValue: {
    type: String,
    default: 'todos'
  }
})

defineEmits(['update:modelValue'])
</script>

<template>
  <section class="filter-bar">
    <div class="filter-bar__inner">

      <span class="filter-bar__label">
        Filtrar per
      </span>

      <div class="filter-bar__select-wrap">
        <select
          id="category-filter"
          class="filter-bar__select"
          :value="modelValue"
          @change="$emit('update:modelValue', $event.target.value)"
        >
          <option value="todos">Seleccionar</option>
          <option value="tecnologia">Tecnologia</option>
          <option value="marketing">Màrqueting</option>
        </select>

        <span class="filter-bar__arrow"></span>
      </div>

    </div>
  </section>
</template>