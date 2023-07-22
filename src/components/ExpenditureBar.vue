<template>
  <div class="chart-container">
    <canvas id="myChart"></canvas>
  </div>
</template>
<script setup>
import { onMounted } from 'vue';

onMounted(() => {
  const ctx = document.getElementById('myChart');
  new Chart(ctx, {
    type: 'bar',
    data: {
      labels: [ '1', '2', '3', '4', '5', '6','7','8','9','10','11','12'],
      datasets: [{
        label: '支出',
        data: [15000, 18000, 20000, 17000, 14000, 15000, 13000],
        borderWidth: 1,
        backgroundColor:[
        '#B0CCED',
        '#B6C6EA',
        '#BBBFE6'
        ]
      }]
    },
    options: {
      scales: {
        y: {
          beginAtZero: true
        }
      }
    }
  });
});
</script>
