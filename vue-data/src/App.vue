<template>
  <div class = "container">
<arrestCard v-for="(arrest) in arrests" :arrest="arrest"></arrestCard>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import arrestCard from './components/arrestCard.vue'
const arrests = ref([])
async function getArrest(){
  try {
    const response = await fetch('https://data.cityofnewyork.us/resource/uip8-fykc.json')
    const data = await response.json()
    arrests.value = data
  } catch (error) {
    console.log(error)
  }
}
onMounted( async () => {
  getArrest()
});
</script>

<style  scoped>

</style>