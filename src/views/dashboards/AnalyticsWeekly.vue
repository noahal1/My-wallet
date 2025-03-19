<script setup>
const weekly = {
    title: '本周消费',
    color: 'secondary',
    icon: 'ri-pie-chart-2-line',
    stats: '$25.6k',
    change: 42,
    subtitle: '后续修改为比上周多了多少',
  }
</script>
<template>
  <div class="match-height">
    <CardStatisticsVertical v-bind="weekly" />
  </div>
</template>

