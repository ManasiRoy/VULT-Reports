
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
          categories: [
            "Jun1",
            "4",
            "7",
            "10",
            "13",
            "16",
            "19",
            "22",
            "25",
            "Jun 30",
          ],
        },
        yaxis: {
          labels: {
            formatter: function (value) {
              return value + "$";
            },
          },
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
          data: [0, 20, 0, 0, 0, 0, 0, 0, 0, 0],
        },
      ],
    };
  },
};
</script>