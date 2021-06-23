<template lang='pug'>
.w-full.flex
  .left-container 
    div 
      Dropdown(:options="reportOptions", :dropOptions="dropOptions")
    div 
      Dropdown(:options="inventoryOptions", :dropOptions="dropOptionsTwo")
  .right-container right
</template>

<script>
import Dropdown from "./Dropdown.vue";

export default {
  name: "Reports",
  components: {
    Dropdown,
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
      dropOptions: {
        Resource: "Resource",
      },
      dropOptionsTwo: {
        InventoryReports: "Inventory Reports",
      },
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
