<template>
  <router-link :to="pkmnPath" class="card">
    <h2>{{ arrest.arrest_key }}</h2>
    <h3>{{ id }}</h3>
  </router-link>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  pokemon: { type: Object, required: true },
  id:      { type: Number, required: true }
})

const pkmnPath = computed(() => {
  return `/PokemonData/${props.pokemon.name}`
})
</script>