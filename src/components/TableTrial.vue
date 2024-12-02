<script setup lang="ts">
import { ref } from "vue";
import TableComponent from "@/components/TableComponent.vue";

// Button Logic
const regenerate = () => {
  console.log('Regenerate clicked');
};

const savePrompts = () => {
  console.log('Save Prompts clicked');
};

const filterValue = ref<string | null>(null);
</script>

<template>
  <v-card
    class="block"
    min-height="1100"
    max-height="1100"
  >
    <v-card-text>
      <!-- Buttons -->
      <div class="buttons-container mb-4">
        <v-btn
          class="left-button regenerate-btn"
          @click="regenerate"
        >
          Regenerate
        </v-btn>
        <v-btn
          class="center-button prompts-btn"
          @click="savePrompts"
        >
          Save prompts in Cancer Bot
        </v-btn>
        <v-autocomplete
          v-model="filterValue"
          :items="['Minimum age', 'Maximum age', 'Stage', 'Treatment']"
          label="Filter by Field"
          clearable
          class="right-button"
          variant="outlined"
        />
      </div>

      <TableComponent :filter="filterValue" />
    </v-card-text>
  </v-card>
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
  max-width: 200px;
  font-family: 'PT Serif', serif;
  color: #4073ff;
}

.regenerate-btn, .prompts-btn {
  border-radius: 10px;
  font-family: 'PT Serif', serif;
  text-transform: none;
  font-weight: bold;
}

.regenerate-btn {
  background: #4073ff;
  color: white;
}

.prompts-btn {
  border: 2px solid #4073ff;
  color: #4073ff;
}
</style>
