<template lang='pug'>
.w-full.flex
  .left-container 
    div 
      Dropdown(:options="reportOptions", :dropOptions="dropOptions")
    div 
      Dropdown(:options="inventoryOptions", :dropOptions="dropOptionsTwo")
    div
      h3.inline-flex.justify-center.py-2.text-sm.font-medium.text-gray-700 Disputes
    div
      h3.inline-flex.justify-center.py-2.text-sm.font-medium.text-gray-700 Cash Drawers
    div
      h3.inline-flex.justify-center.py-2.text-sm.font-medium.text-gray-700 Activity Log
    div 
      Dropdown(:options="settingsOptions", :dropOptions="settingOptionsName")
  .right-container 
    .mb-4.pb-4.border-b-2.border-gray-200.w-full.flex
      Dropdown.px-4.rounded-md.border.border-gray-200.shadow-sm.py-2.bg-gray-200.mr-3(
        :options="allOptions",
        :dropOptions="allOptionsName"
      )
      Dropdown.px-4.rounded-md.border.border-gray-200.shadow-sm.py-2.bg-gray-200.mr-3(
        :options="summaryOptions",
        :dropOptions="summaryOptionsName"
      )
      Dropdown.px-4.rounded-md.border.border-gray-200.shadow-sm.py-2.bg-gray-200.mr-3(
        :options="displayOptions",
        :dropOptions="displayOptionsName"
      )
      Dropdown.px-4.rounded-md.border.border-gray-200.shadow-sm.py-2.bg-gray-200.mr-3(
        :options="filterOptions",
        :dropOptions="filterOptionsName"
      )
      button.px-4.rounded-md.border.border-gray-200.shadow-sm.py-2.bg-gray-200.ml-auto Export
    .chart-outr
      h1.text-2xl.font-sans.font-semibold.text-gray-700.mb-6 Jun.1,2021-Jun.30,2021
      .mb-7
        h3.text-lg.font-sans.font-semibold.text-gray-700 Jun.2021
        apexchartareadate
      h3.text-lg.font-sans.font-semibold.text-gray-700 Day of Week
    .w-full.flex
      .apexchart-bar-wrap
        apexchart
      .apexchart-area-wrap
        apexchartarea
</template>

<script>
import Dropdown from "./Dropdown.vue";
import apexchart from "./apexChart.vue";
import apexchartarea from "./apexChartArea.vue";
import apexchartareadate from "./apexChartAreaDate.vue";

export default {
  name: "Reports",
  components: {
    Dropdown,
    apexchart,
    apexchartarea,
    apexchartareadate,
  },
  // props: {
  //   msg: String,
  // },

  data() {
    return {
      reportOptions: {
        selectedR: "R",
        Report: "Good",
        Reporttwo: "Bad",
      },
      inventoryOptions: {
        inselectedR: "R",
        inReport: "Good",
        inReporttwo: "Bad",
      },
      settingsOptions: {
        Settings: "Settings",
        SettingsTwo: "SettingsTwo",
      },
      allOptions: {
        allOptions: "allOptions",
        allOptionsTwo: "allOptionsTwo",
      },
      summaryOptions: {
        summaryOptions: "summaryOptions",
        summaryOptionsTwo: "summaryOptionsTwo",
      },
      displayOptions: {
        displayOptions: "displayOptions",
        displayOptionsTwo: "displayOptionsTwo",
      },
      filterOptions: {
        filterOptions: "filterOptions",
        filterOptionsTwo: "filterOptionsTwo",
      },

      dropOptions: {
        Resource: "Resource",
      },
      dropOptionsTwo: {
        InventoryReports: "Inventory Reports",
      },
      settingOptionsName: {
        Setting: "Settings",
      },
      allOptionsName: {
        Allday: "All Day",
      },
      summaryOptionsName: {
        summary: "summaryOptions",
      },
      displayOptionsName: {
        Display: "displayOptions",
      },
      filterOptionsName: {
        Filter: "filterOptions",
      },
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
