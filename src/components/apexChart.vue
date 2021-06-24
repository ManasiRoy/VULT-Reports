
<template>
  <div id="chart">
    <apexchart type="bar" :options="chartOptions" :series="series"></apexchart>
  </div>
</template>

<script>
import VueApexCharts from "vue3-apexcharts";
export default {
  components: {
    apexchart: VueApexCharts,
  },
  data: function () {
    return {
      chartOptions: {
        chart: {
          width: "100%",
          height: 300,
          id: "vuechart-example",
        },
        xaxis: {
          categories: ["S", " M", "T", "W", "T", "F", "S"],
        },
        yaxis: {
          tickAmount: 3,
          max: 30,
          // Include a dollar sign in the ticks
          callback: function (value) {
            return "$" + value.toFixed(2);
          },
        },
      },
      series: [
        {
          name: "weekly credit",
          data: [1, 1, 1, 1, 20, 1, 1, 1],
        },
      ],
    };
  },
};
</script>