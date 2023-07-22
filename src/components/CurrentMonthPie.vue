<template>
  <div class="chart-container">
  <canvas id="myChart2"></canvas>
  </div>
</template>
<script setup>
import { onMounted } from 'vue';

onMounted(() => {
  const ctx = document.getElementById('myChart2');
  new Chart(ctx, {
    type: 'pie',
    data: {
  labels: [
    '飲食',
    '交通',
    '日用品'
  ],
  datasets: [{
    label: 'My First Dataset',
    data: [300, 50, 100],
    backgroundColor: [
      '#C5B1DF',
      '#E2D4DF',
      '#FFF6DE'
    ],
    hoverOffset: 4
  }]
},
  });
});
</script>
