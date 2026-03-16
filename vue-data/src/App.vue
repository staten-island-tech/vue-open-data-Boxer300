<template>
  <div>

  </div>
</template>

<script setup>
import { ref, onMounted }
const arrest ref({})
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