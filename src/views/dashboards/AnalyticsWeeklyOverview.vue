<script setup>
import { hexToRgb } from '@core/utils/colorConverter'
import { useTheme } from 'vuetify'

const vuetifyTheme = useTheme()

const options = computed(() => {
  const currentTheme = ref(vuetifyTheme.current.value.colors)
  const variableTheme = ref(vuetifyTheme.current.value.variables)
  const disabledColor = `rgba(${ hexToRgb(currentTheme.value['on-surface']) },${ variableTheme.value['disabled-opacity'] })`
  const borderColor = `rgba(${ hexToRgb(String(variableTheme.value['border-color'])) },${ variableTheme.value['border-opacity'] })`
  
  return {
    chart: {
      offsetY: -10,
      offsetX: -15,
      parentHeightOffset: 0,
      toolbar: { show: false },
    },
    plotOptions: {
      bar: {
        borderRadius: 6,
        distributed: true,
        columnWidth: '30%',
      },
    },
    stroke: {
      width: 2,
      colors: [currentTheme.value.surface],
    },
    legend: { show: false },
    grid: {
      borderColor,
      strokeDashArray: 7,
      xaxis: { lines: { show: false } },
    },
    dataLabels: { enabled: false },
    colors: [
      currentTheme.value['track-bg'],
      currentTheme.value['track-bg'],
      'rgba(var(--v-theme-primary),1)', 
      currentTheme.value['track-bg'],
      currentTheme.value['track-bg'],
      currentTheme.value['track-bg'],
    ],
    states: {
      hover: { filter: { type: 'none' } },
      active: { filter: { type: 'none' } },
    },
    xaxis: {
      categories: [
        'Mon',
        'Tue',
        'Wed',
        'Thu',
        'Fri',
        'Sat',
        'Sun',
      ],
      tickPlacement: 'on',
      labels: { 
        show: true,  
        style: {
          colors: disabledColor,
          fontSize: '12px',
        },
      },
      crosshairs: { opacity: 0 },
      axisTicks: { show: false },
      axisBorder: { show: false },
    },
    yaxis: {
      show: true,
      tickAmount: 4,
      labels: {
        style: {
          colors: disabledColor,
          fontSize: '13px',
        },
        formatter: value => `¥${value}`, 
      },
    },
    responsive: [[
      {
        breakpoint: 500,
        options: { plotOptions: { bar: { columnWidth: '35%' } } },
      },
      {
        breakpoint: 300,
        options: { plotOptions: { bar: { columnWidth: '45%' } } },
      },
    ]],
  }
})

const series = [{
  name: '消费金额',
  data: [
    800,  
    650,  
    1200,  
    700,   
    950,   
    1500,  
    1800,   
  ],
}]
</script>

<template>
  <VCard>
    <VCardItem>
      <VCardTitle>周消费</VCardTitle>  <!-- 标题修改 -->

      <template #append>
        <div class="me-n3">
          <MoreBtn />
        </div>
      </template>
    </VCardItem>

    <VCardText>
      <VueApexCharts
        type="bar"
        :options="options"
        :series="series"
        :height="200"
      />

      <div class="d-flex align-center mb-5 gap-x-4">
        <h4 class="text-h4">
          ¥7,400
        </h4>
        <p class="mb-0">
          本周消费较上周 <span class="text-success">减少12%</span> <span class="text-high-emphasis">👍</span>
        </p>
      </div>

      <VBtn
        block
        color="primary"
      >
        消费明细
      </VBtn>
    </VCardText>
  </VCard>
</template>
