<script setup>
import { useTheme } from 'vuetify'
import { hexToRgb } from '@core/utils/colorConverter'

const vuetifyTheme = useTheme()

const options = computed(() => {
  const currentTheme = ref(vuetifyTheme.current.value.colors)
  const variableTheme = ref(vuetifyTheme.current.value.variables)
  const secondaryTextColor = `rgba(${ hexToRgb(currentTheme.value['on-surface']) },${ variableTheme.value['medium-emphasis-opacity'] })`
  const disabledColor = `rgba(${ hexToRgb(currentTheme.value['on-surface']) },${ variableTheme.value['disabled-opacity'] })`
  const borderColor = `rgba(${ hexToRgb(String(variableTheme.value['border-color'])) },${ variableTheme.value['border-opacity'] })`
  
  return {
    chart: {
      parentHeightOffset: 0,
      toolbar: { show: false },
    },
    colors: [
      currentTheme.value.primary,
      currentTheme.value.info,
    ],
    plotOptions: {
      radar: {
        size: 110,
        polygons: {
          strokeColors: borderColor,
          connectorColors: borderColor,
        },
      },
    },
    legend: {
      labels: { colors: secondaryTextColor },
      fontSize: '15px',
      markers: {
        width: '10px',
        height: '10px',
      },
    },
    fill: {
      type: 'gradient',
      gradient: {
        shade: 'dark',
        gradientToColors: [
          currentTheme.value.primary,
          currentTheme.value.info,
        ],
        shadeIntensity: 1,
        type: 'vertical',
        opacityFrom: 1,
        opacityTo: 0.9,
        stops: [
          0,
          100,
        ],
      },
    },
    labels: [
      '餐饮',
      '交通',
      '娱乐',
      '购物',
      '住房',
      '其他',
    ],
    markers: { size: 0 },
    xaxis: {
      labels: {
        show: true,
        style: {
          fontSize: '13px',
          colors: [
            disabledColor,
            disabledColor,
            disabledColor,
            disabledColor,
            disabledColor,
            disabledColor,
          ],
        },
      },
    },
    yaxis: { show: false },
    grid: { show: false },
  }
})

const series = [
  {
    name: '预算',
    data: [
      500,
      300,
      200,
      400,
      1000,
      200,
    ],
  },
  {
    name: '支出',
    data: [
      450,
      320,
      180,
      350,
      950,
      250,
    ],
  },
]
</script>

<template>
  <VCard>
    <VCardItem>
      <VCardTitle>花费分布图</VCardTitle>

      <template #append>
        <div class="me-n3">
          <MoreBtn />
        </div>
      </template>
    </VCardItem>

    <VCardText>
      <VueApexCharts
        type="radar"
        :options="options"
        :series="series"
        :height="295"
      />
    </VCardText>
  </VCard>
</template>
