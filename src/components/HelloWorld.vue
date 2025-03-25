<template>
  <div id="spreadsheet" style="width: 100%; height: 500px;"></div>
</template>

<script>
import Spreadsheet from "x-data-spreadsheet";
import "x-data-spreadsheet/dist/xspreadsheet.css";

export default {
  name: "SpreadsheetViewer",
  mounted() {
    const sheet = new Spreadsheet("#spreadsheet", {
      showToolbar: true,
      showGrid: true,
      showContextmenu: true,
    }).loadData({
      // sample data
      styles: [],
      sheets: [
        {
          name: "Sheet1",
          freeze: "A1",
          styles: [],
          merges: [],
          rows: {
            0: {
              cells: {
                0: { text: "Hello" },
                1: { text: "World" },
              },
            },
          },
        },
      ],
    });

    // You can access the data later like this:
    // const data = sheet.getData();
  },
};
</script>

<style>
/* Optional: make sure the spreadsheet fills the container */
#spreadsheet {
  border: 1px solid #ccc;
}
</style>
