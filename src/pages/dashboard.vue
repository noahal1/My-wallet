<script setup>
import draggable from 'vuedraggable';

const componentsList = ref([
  { id: 1, name: 'AnalyticsAward', cols: { base: 12, md: 4 } , _customHeight: { base: '200px', md: 'auto' }},
  { id: 2, name: 'AnalyticsTransactions', cols: { base: 12, md: 8 } , _customHeight: { base: '200px', md: 'auto' }},
  { id: 3, name: 'AnalyticsWeeklyOverview', cols: { base: 12, md: 4, sm: 6 }, _customHeight: { base: '200px', md: 'auto' } },
  { id: 4, name: 'AnalyticsTotalEarning', cols: { base: 12, md: 4 , sm: 6 } , _customHeight: { base: '200px', md: 'auto' }},
  { id: 5, name: 'AnalyticsTotalProfit', cols: { base: 12, md: 2, sm: 6 }, _customHeight: { base: '200px', md: 'auto' } },
  { id: 6, name: 'AnalyticsFlow', cols: { base: 12,md: 2,  sm: 6 }, _customHeight: { base: '200px', md: 'auto' }  },
  { id: 7, name: 'AnalyticsWeekly', cols: { base: 12, md: 2, sm: 6 } , _customHeight: { base: '200px', md: 'auto' } },
  { id: 8, name: 'AnalyticsSessionBarCharts', cols: { base: 12, md: 2, sm: 6 } , _customHeight: { base: '200px', md: 'auto' } },
  { id: 9, name: 'AnalyticsPerformance', cols: { base: 12, md: 4 }, _customHeight: { base: '200px', md: 'auto' }  },
  { id: 10, name: 'AnalyticsDepositWithdraw', cols: { base: 12, md: 8 } },
  { id: 11, name: 'AnalyticsSalesByCountries', cols: { base: 12, md: 4 } },
  { id: 12, name: 'AnalyticsUserTable', cols: { base: 12, md: 8 } }
])
const components = {
    AnalyticsAward: defineAsyncComponent(() => import('@/views/dashboards/AnalyticsAward.vue')),
    AnalyticsTransactions: defineAsyncComponent(() => import('@/views/dashboards/AnalyticsTransactions.vue')),
    AnalyticsWeeklyOverview: defineAsyncComponent(() => import('@/views/dashboards/AnalyticsWeeklyOverview.vue')),
    AnalyticsTotalEarning: defineAsyncComponent(() => import('@/views/dashboards/AnalyticsTotalEarning.vue')),
    AnalyticsTotalProfit: defineAsyncComponent(() => import('@/views/dashboards/AnalyticsTotalProfit.vue')),
    AnalyticsSessionBarCharts: defineAsyncComponent(() => import('@/views/dashboards/AnalyticsSessionsBarCharts.vue')),
    AnalyticsPerformance: defineAsyncComponent(() => import('@/views/dashboards/AnalyticsPerformance.vue')),
    AnalyticsDepositWithdraw: defineAsyncComponent(() => import('@/views/dashboards/AnalyticsDepositWithdraw.vue')),
    AnalyticsSalesByCountries: defineAsyncComponent(() => import('@/views/dashboards/AnalyticsSalesByCountries.vue')),
    AnalyticsUserTable: defineAsyncComponent(() => import('@/views/dashboards/AnalyticsUserTable.vue')),
    AnalyticsWeekly: defineAsyncComponent(() => import('@/views/dashboards/AnalyticsWeekly.vue')),
    AnalyticsFlow: defineAsyncComponent(() => import('@/views/dashboards/AnalyticsFlow.vue'))
}
const handleDragEnd = () => {
  componentsList.value = [...componentsList.value];
}
</script>

<template>
  <v-row>
  <div>
    <draggable 
      v-model="componentsList" 
      item-key="id"
      tag="div" 
      class="v-row mx-n2"
      :no-gutters="false"
      handle=".drag-handle"
      :group="{ name: 'dashboard' }"
      :animation="600"
      @end="handleDragEnd"
    >
      <template #item="{ element }">
        <v-col 
          :cols="element.cols.base"
          :md="element.cols.md"
          class="position-relative match-height"
        >
          <div class="drag-handle">
            <v-icon icon="ri-drag-move-2-line" size="15" />
          </div>
          <div class="component-container">
            <component :is="components[element.name]" :style="{ height: element.cols._customHeight || '100%' }"/>
          </div>
        </v-col>
      </template>
    </draggable>
  </div>
  </v-row>
</template>
<style lang="scss">
@use "@core/scss/template/libs/apex-chart.scss";
.component-container {
  height: 100%;
  transition: height 0.3s ease;
  min-height: 100px;
}
.v-row {
  display: flex;
  flex-wrap: wrap;
  margin-top: -10px; 
  margin-bottom: -10px;
  
}
.v-col {
  display: flex;
  flex-direction: column;
  padding-top: 10px;
  padding-bottom: 10px;

}
.sortable-ghost {
  opacity: 0.5;
  min-height: 0;
  background: rgba(var(--v-theme-primary), 0.1);
  border: 2px dashed rgba(var(--v-theme-primary), 1);
}
.drag-handle {
  position: absolute;
  padding: 8px;
  right: 8px;
  top: 8px;
  cursor: move;
  z-index: 100;
  border-radius: 4px;
  background: rgba(var(--v-theme-surface), 1);
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  transition: all 0.2s;
  
  &:hover {
    color: rgba(var(--v-theme-primary), 1);
    transform: scale(1.1);
  }
  &::after {
    font-size: 0.75rem;
    margin-left: 4px;
  }
}
</style>
