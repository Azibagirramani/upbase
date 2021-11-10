<template>
  <apexchart
    class="chart-sharp"
    :options="options"
    :series="series"
  ></apexchart>
</template>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    series: {
      type: Array,
      default: () => [],
    },
    options: {
      type: Object,
      default: () => ({}),
    },
  },
});
</script>

<style lang="scss" scoped>
.chart-sharp {
  width: 100%;
  height: 50px !important;
}
</style>
