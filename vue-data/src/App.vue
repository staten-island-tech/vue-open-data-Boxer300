<template>
  <div class = "container">
<arrestCard v-for="(arrest) in arrests" :key="arrest.arrest_key"></arrestCard>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
const arrest = ref([])
async function getArrest(){
  try {
    const response = await fetch('https://data.cityofnewyork.us/resource/uip8-fykc.json')
    const data = await response.json()
    arrest.value = data
  } catch (error) {
    console.log(error)
  }
}
onMounted(() => {
  getArrest()
});
</script>

<style  scoped>

</style>