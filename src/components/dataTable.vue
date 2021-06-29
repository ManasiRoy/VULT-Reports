<template>
  <table-lite
    :has-checkbox="false"
    :is-loading="table.isLoading"
    :columns="table.columns"
    :rows="table.rows"
    :total="table.totalRecordCount"
    :hide-default-footer="true"
  ></table-lite>
</template>

<script>
import { defineComponent, reactive } from "vue";
import TableLite from "vue3-table-lite";

export default defineComponent({
  name: "dataTable",
  components: {
    TableLite,
  },
  setup() {
    const table = reactive({
      isLoading: false,
      isReSearch: false,
      isPagingInfo: false,
      columns: [
        {
          label: "Name",
          field: "name",
        },
        {
          label: "Total Collected",
          field: "totalCollected",
        },
        {
          label: "Auto Grat",
          field: "AutoGrat",
        },
        {
          label: "Net Sales",
          field: "netSales",
        },
        {
          label: "Avg Sales",
          field: "avgSales",
        },
        {
          label: "Covers",
          field: "covers",
        },
        {
          label: "Sale Count",
          field: "salecount",
        },
        {
          label: "Paid Hours",
          field: "pHours",
        },
        {
          label: "Sales / Hours",
          field: "sHours",
        },
        {
          label: "Tips",
          field: "tips",
        },
        {
          label: "Commission",
          field: "commission",
        },
      ],
      rows: [
        {
          name: "tariq koshy",
          totalCollected: "$15.50",
          AutoGrat: "$0.00",
          netSales: "$15.20",
          avgSales: "$1.69",
          covers: "0",
          pHours: "27.80",
          sHours: "$0.55",
          tips: "$0.00",
          commission: "$0.00",
        },
      ],
    });

    return {
      table,
    };
  },
});
</script>

<style>
</style>