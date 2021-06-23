<template>
  <Chart
    :size="{ width: 500, height: 420 }"
    :data="data"
    :margin="margin"
    :direction="direction"
    :axis="axis"
  >
    <template #layers>
      <Grid strokeDasharray="1,1" />
      <Area
        :dataKeys="['name', 'pl']"
        type="monotone"
        :areaStyle="{ fill: 'url(#grad)' }"
      />
      <Line
        :dataKeys="['name', 'pl']"
        type="monotone"
        :lineStyle="{
          stroke: '#296df6',
        }"
      />
      <Marker
        v-if="marker"
        :value="1000"
        label="Mean."
        color="green"
        strokeWidth="1"
        strokeDasharray="1 1"
      />
      <defs>
        <linearGradient id="grad" gradientTransform="rotate(90)">
          <stop offset="0%" stop-color="#be90ff" stop-opacity="1" />
          <stop offset="100%" stop-color="white" stop-opacity="0.8" />
        </linearGradient>
      </defs>
    </template>

    <template #widgets>
      <Tooltip
        borderColor="rgba(0,0,0,0.2)"
        :config="{
          pl: { color: '#f00' },
          avg: { hide: true },
          inc: { hide: true },
        }"
      />
    </template>
  </Chart>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import { Chart, Grid, Line } from "vue3-charts";
import { plByMonth } from "./data";

export default defineComponent({
  name: "LineChart",
  components: { Chart, Grid, Line },
  setup() {
    const data = ref(plByMonth);
    const direction = ref("horizontal");
    const margin = ref({
      left: 0,
      top: 20,
      right: 20,
      bottom: 0,
    });

    const axis = ref({
      primary: {
        type: "band",
      },
      secondary: {
        domain: ["dataMin", "dataMax + 10"],
        type: "linear",
        ticks: 4,
      },
      responsive: true,
    });

    return { data, direction, margin, axis };
  },
});
</script>