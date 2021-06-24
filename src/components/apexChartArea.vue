
<template>
  <div id="chart">
    <apexchart
      type="area"
      height="380"
      :options="chartOptions"
      :series="series"
    ></apexchart>
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
          id: "vuechart-example",
        },
        xaxis: {
          categories: ["12am", "3", "6", "9", "12pm", "3", "6", "9"],
        },
        yaxis: {
          tickAmount: 2,
          max: 20,
          // Include a dollar sign in the ticks
          callback: function (value) {
            return "$" + value.toFixed(2);
          },
        },
      },
      series: [
        {
          name: "weekly credit",
          data: [0, 0, 0, 5, 20, 0, 0, 0, 0],
        },
      ],
    };
  },
};
</script>