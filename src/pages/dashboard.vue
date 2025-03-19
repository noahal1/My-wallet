<script setup>
import { defineAsyncComponent } from 'vue';
import draggable from 'vuedraggable';

const componentsList = ref([
  { id: 1, name: 'AnalyticsAward', cols: { cols: 12, md: 4 }, width: 2, height:1 },
  { id: 2, name: 'AnalyticsTransactions', cols: { cols: 12, md: 8 }, _customHeight: { base: 'auto', md: 'auto' }, width: 2, height: 1 },
  { id: 3, name: 'AnalyticsWeeklyOverview', cols: { cols: 12, md: 4, sm: 6 }, _customHeight: { base: 'auto', md: 'auto' }, width: 1, height: 1 },
  { id: 4, name: 'AnalyticsTotalEarning', cols: { cols: 12, md: 4, sm: 6 }, _customHeight: { base: 'auto', md: 'auto' }, width: 1, height: 1 },
  { id: 5, name: 'AnalyticsTotalProfit', cols: { cols: 12, md: 2, sm: 6 }, _customHeight: { base: 'auto', md: 'auto' }, width: 1, height: 1 },
  { id: 6, name: 'AnalyticsFlow', cols: { cols: 12, md: 2, sm: 6 }, _customHeight: { base: 'auto', md: 'auto' }, width: 1, height: 1 },
  { id: 7, name: 'AnalyticsWeekly', cols: { cols: 12, md: 2, sm: 6 }, _customHeight: { base: 'auto', md: 'auto' }, width: 1, height: 1 },
  { id: 8, name: 'AnalyticsSessionBarCharts', cols: { cols: 12, md: 2, sm: 6 }, _customHeight: { base: 'auto', md: 'auto' }, width: 1, height: 1 },
  { id: 9, name: 'AnalyticsPerformance', cols: { cols: 12, md: 4 }, _customHeight: { base: 'auto', md: 'auto' }, width: 1, height: 1 },
  { id: 10, name: 'AnalyticsDepositWithdraw', cols: { cols: 12, md: 8 }, width: 2, height: 1 },
  { id: 11, name: 'AnalyticsSalesByCountries', cols: { cols: 12, md: 4 }, width: 1, height: 1 },
  { id: 12, name: 'AnalyticsUserTable', cols: { cols: 12, md: 8 }, width: 2, height: 1 },
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
  <draggable
    v-model="componentsList"
    item-key="id"
    tag="div"
    class="v-row"
    :no-gutters="false"
    handle=".drag-handle"
    :group="{ name: 'dashboard' }"
    :animation="600"
    @end="handleDragEnd"
  >
    <template #item="{ element }">
      <v-col
        :cols="element.cols.cols"
        :md="element.cols.md"
        :sm="element.cols.sm"
        class="position-relative match-height"
        :style="{
          height: element._customHeight?.base,
          '@media (min-width: 960px)': { height: element._customHeight?.md }
        }"
        :data-width="element.width"
        :data-height="element.height"
      >
        <div class="drag-handle">
          <v-icon icon="ri-drag-move-2-line" size="15" />
        </div>
        <div class="component-container">
          <component :is="components[element.name]" v-bind="element.props || {}" />
        </div>
      </v-col>
    </template>
  </draggable>
</template>

<style lang="scss">
@use "@core/scss/template/libs/apex-chart.scss";

.dashboard-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr); // 定义 12 列的栅格
  grid-gap: 10px; // 设置栅格间距
  padding: 10px; // 可选：添加一些内边距
  align-items: start; // 确保网格项顶部对齐
}

.grid-item {
  position: relative;
  display: flex;
  flex-direction: column;
  min-height: 100px; // 确保即使内容很少也有最小高度
}

.component-container {
  flex-grow: 1; // 让组件容器占据剩余空间
  transition: height 0.3s ease;
  height: 100%; // 确保组件容器的高度与 grid-item 一致
}

.sortable-ghost {
  opacity: 0.5;
  min-height: 0;
  background: rgba(var(--v-theme-primary), 0.1);
  border: 2px dashed rgba(var(--v-theme-primary), 1);
}

.drag-handle {
  position: absolute;
  padding: 5px;
  right: 10px;
  top: 10px;
  cursor: move;
  z-index: 100;
  border-radius: 4px;
  background: rgba(var(--v-theme-surface), 1);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
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
