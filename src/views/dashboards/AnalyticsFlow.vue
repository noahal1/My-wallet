<script setup>
const flow = {
    title: '网站总访问人数',
    color: 'primary',
    icon: 'ri-file-word-2-line',
    stats: '862',
    change: -18,
    subtitle: 'Yearly Project',
  }
</script>

<template>
  <div class="match-height">
    <CardStatisticsVertical v-bind="flow" />
  </div>
</template>
<style lang="scss">
@use "@core/scss/template/libs/apex-chart.scss";
</style>
