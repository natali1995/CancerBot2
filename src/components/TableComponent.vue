<script setup lang="ts">
import { ref, computed, defineProps } from 'vue';

const props = defineProps<{ filter: string | null }>();

// Table Data
// Static Table Data
const tableData = ref([
  { field: "Minimum age", question: "What is minimum age?", answer: "18" },
  { field: "Maximum age", question: "What is maximum age?", answer: "80" },
  { field: "Stage", question: "What is stage?", answer: "II" },
  { field: "Treatment", question: "Other", answer: "Yes" },
  { field: "Minimum age", question: "What is minimum age?", answer: "18" },
  { field: "Maximum age", question: "What is maximum age?", answer: "80" },
  { field: "Stage", question: "What is stage?", answer: "II" },
  { field: "Treatment", question: "Other", answer: "Yes" },
  { field: "Minimum age", question: "What is minimum age?", answer: "18" },
  { field: "Maximum age", question: "What is maximum age?", answer: "80" },
  { field: "Stage", question: "What is stage?", answer: "II" },
  { field: "Treatment", question: "Other", answer: "Yes" },
]);

const filteredTableData = computed(() =>
  props.filter
    ? tableData.value.filter((row) =>
      row.field.toLowerCase().includes(props.filter!.toLowerCase())
    )
    : tableData.value
);

</script>

<template>
  <!-- Table -->

  <div class="table-container mt-12">
    <table class="custom-table">
      <!-- Table Header -->
      <thead>
        <tr>
          <th class="custom-header">
            Field
          </th>
          <th class="custom-header">
            Question
          </th>
          <th class="custom-header">
            Answer
          </th>
        </tr>
      </thead>

      <!-- Table Body -->
      <tbody>
        <tr
          v-for="(row, index) in filteredTableData"
          :key="index"
        >
          <!-- Field Column -->
          <td class="table-cell">
            {{ row.field }}
          </td>

          <!-- Question Column with Multiline Input -->
          <td class="table-cell question-column">
            <v-textarea
              variant="outlined"
              dense
              class="custom-v-textarea"
              rows="3"
              :placeholder="row.question"
              no-resize
            />
          </td>

          <!-- Answer Column -->
          <td class="table-cell">
            {{ row.answer }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
@font-face {
  font-family: 'EBGaramond';
  src: url('@/assets/fonts/EBGaramond-Bold.ttf') format('truetype');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: 'PT Serif';
  src: url('@/assets/fonts/PTSerif-Regular.ttf') format('truetype');
  font-weight: normal;
  font-style: normal;
}

/* Table Container */
.table-container {
  overflow-x: auto;
  overflow-y: auto; /* Enable vertical scrolling for the table */
  max-height: 950px; /* Set maximum height for scrolling */
}

/* Table Styling */
.custom-table {
  width: 100%;
  border-collapse: collapse;
  text-align: left;
}

/* Header Styling */
.custom-header {
  text-align: center;
  font-weight: bold;
  padding: 10px;
  font-family: 'Garamond', serif;
  font-size: 1.4rem;
  color: #4073ff;
  border-bottom: 2px solid #868686; /* Line below headers */
}


/* Row Line Divider */
.custom-table tr {
  border-bottom: 2px solid #868686; /* Lines dividing rows */
}

.custom-table tr:first-child {
  border-top: 2px solid #868686; /* Line above header */
}

.custom-table tr:last-child {
  border-bottom: 2px solid #868686; /* Line below the last row */
}

/* Column Width for Question */
.question-column {
  width: 40%; /* Reduced width for Question column */
}

/* Cell Styling */
.table-cell {
  padding: 10px;
  text-align: center;
  vertical-align: middle;
  font-family: 'PT Serif', serif;
  font-weight: bold;
}

/* Vuetify Textarea Styling */
.custom-v-textarea {
  width: 100%;
  margin: 0;
  background: none; /* Remove background */
  resize: none; /* Disable resize (removes triangle) */
  box-sizing: border-box;
}
</style>
