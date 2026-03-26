<template>
  <div style="max-width: 600px;">
    <Bar :data="chartData" />
  </div>
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

// 🔥 REQUIRED
ChartJS.register(BarElement, CategoryScale, LinearScale, Tooltip, Legend)

const props = defineProps({
  data: Object
})

// chart format
const chartData = computed(() => ({
  labels: Object.keys(props.data || {}),
  datasets: [
    {
      label: 'Arrests',
      data: Object.values(props.data || {}),
    }
  ]
}))
</script>