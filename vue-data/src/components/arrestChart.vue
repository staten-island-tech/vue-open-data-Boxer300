<template>
  <Bar :data="chartData" />
</template>

<script setup>
import { computed } from 'vue'
import { Bar } from 'vue-chartjs'
import {
  Chart as ChartJS,
  BarElement,
  CategoryScale,
  LinearScale,
  Tooltip,
  Legend
} from 'chart.js'

ChartJS.register(BarElement, CategoryScale, LinearScale, Tooltip, Legend)

const props = defineProps({
  data: Object
})

const chartData = computed(() => {
  return {
    labels: Object.keys(props.data),
    datasets: [
      {
        label: 'Arrests by Race',
        data: Object.values(props.data),
      }
    ]
  }
})
</script>