<script setup lang="ts">
import { ref } from 'vue';

const headers = ref([
  { text: 'Field', value: 'field' },
  { text: 'Question', value: 'question' },
  { text: 'Answer', value: 'answer' },
]);

// Table Data
const tableData = ref([
  { field: 'Field 1', question: 'What is Field 1?', answer: 'Answer 1' },
  { field: 'Field 2', question: 'What is Field 2?', answer: 'Answer 2' },
  { field: 'Field 3', question: 'What is Field 3?', answer: 'Answer 3' },
]);


// Button Logic
const regenerate = () => {
  console.log('Regenerate clicked');
};

const savePrompts = () => {
  console.log('Save Prompts clicked');
};

const filterByField = () => {
  // Sort table data by "field"
  tableData.value.sort((a, b) => a.field.localeCompare(b.field));
  console.log('Filter by Field clicked');
};
</script>

<template>
  <v-card
    class="block"
    max-height="auto"
  >
    <v-card-text>
      <!-- Buttons -->
      <div class="buttons-container mb-4">
        <v-btn
          color="primary"
          class="left-button"
          @click="regenerate"
        >
          Regenerate
        </v-btn>
        <v-btn
          color="secondary"
          class="center-button"
          @click="savePrompts"
        >
          Save Prompts
        </v-btn>
        <v-btn
          color="success"
          class="right-button"
          @click="filterByField"
        >
          Filter by Field
        </v-btn>
      </div>

      <!-- Table -->

      <v-data-table
        :headers="headers"
        :items="tableData"
        class="custom-table"
        hide-default-footer
      >
        <!-- Editable Header -->
        <template v-slot:header="{ headers }">
          <thead>
          <tr>
            <th v-for="header in headers" :key="header.value" class="custom-header">
              <v-text-field
                v-model="header.text"
                dense
                outlined
                class="header-editor"
                placeholder="Edit header"
              ></v-text-field>
            </th>
          </tr>
          </thead>
        </template>

        <!-- Table Body -->
        <template v-slot:body="{ items }">
          <tr v-for="(item, index) in items" :key="index" class="table-row">
            <!-- Field Column -->
            <td class="text-center">
              <v-text-field
                v-model="item.field"
                dense
                outlined
                placeholder="Enter field"
              ></v-text-field>
            </td>

            <!-- Question Column -->
            <td class="text-center">
              <v-textarea
                v-model="item.question"
                dense
                outlined
                placeholder="Enter question"
                rows="2"
                class="no-resize"
              ></v-textarea>
            </td>

            <!-- Answer Column -->
            <td class="text-center">
              <span class="custom-text">{{ item.answer }}</span>
            </td>
          </tr>
        </template>
      </v-data-table>



<!--      <v-data-table-->
<!--        :header="headers"-->
<!--        :items="tableData"-->
<!--        class="custom-table"-->
<!--        hide-default-footer-->
<!--        disable-sort-->
<!--      >-->
<!--        &lt;!&ndash; Custom Rows &ndash;&gt;-->
<!--        <template #body="{ items }">-->
<!--          <tr-->
<!--            v-for="(item, index) in items"-->
<!--            :key="index"-->
<!--            class="table-row"-->
<!--          >-->
<!--            &lt;!&ndash; Field Column &ndash;&gt;-->
<!--            <td>{{ item.field }}</td>-->

<!--            &lt;!&ndash; Question Column &ndash;&gt;-->
<!--            <td>-->
<!--              <v-textarea-->
<!--                v-model="item.question"-->
<!--                dense-->
<!--                variant="outlined"-->
<!--                placeholder="Enter your question"-->
<!--                rows="2"-->
<!--                no-resize-->
<!--                class="mt-5"-->
<!--              >-->
<!--              </v-textarea>-->
<!--            </td>-->

<!--            &lt;!&ndash; Answer Column &ndash;&gt;-->
<!--            <td>{{ item.answer }}</td>-->
<!--          </tr>-->
<!--        </template>-->
<!--      </v-data-table>-->
    </v-card-text>
  </v-card>
</template>

<style scoped>
/* Apply styles for the table block */
.block {
  flex: 1;
  border: solid 2px #4073ff;
  padding: 16px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  text-align: center; /* Center content within the blocks */
}

/* Buttons container styling */
.buttons-container {
  display: flex;
  justify-content: space-between; /* Distribute buttons */
  align-items: center;
  margin-bottom: 16px; /* Add space between buttons and the table */
}

/* Button Styling */
.left-button,
.center-button,
.right-button {
  width: auto; /* Ensure buttons fit their content */
  min-width: 120px; /* Add consistent minimum width */
  text-align: center; /* Align text in the button */
}

.center-button {
  margin: 0 auto; /* Center the button */
}
.right-button {
  justify-self: end; /* Align the button to the right */
}

/* Custom table styling */
.custom-table {
  border-collapse: collapse;
  width: 100%;
}

.custom-header {
  font-weight: bold;
  text-align: center;
  background-color: #f5f5f5;
  padding: 10px;
  border-bottom: 2px solid #ccc;
}

/* Row Styling */
.table-row {
  border-bottom: 1px solid #ccc; /* Add a line between rows */
}

.table-row:last-child {
  border-bottom: none; /* Remove line under the last row */
}

/* Padding for Table Cells */
td {
  padding: 8px;
  vertical-align: middle;
}
</style>
