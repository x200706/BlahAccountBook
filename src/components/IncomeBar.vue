<script setup>
import { onMounted } from 'vue';

const labelsList = [ '1', '2', '3', '4', '5', '6','7','8','9','10','11','12']
const dataList = [39400, 57400, 39400, 47400, 39400, 42400, 39400]

onMounted(() => {
  const ctx = document.getElementById('myChart3');
  new Chart(ctx, {
    type: 'bar',
    data: {
      labels: labelsList,
      datasets: [{
        label: '收入',
        data: dataList,
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
<template>
  <div class="main-chart-container">
    <canvas id="myChart3"></canvas>
  </div>
</template>