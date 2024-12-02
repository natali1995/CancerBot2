<template>
  <v-app>
    <v-main>
      <v-container>
        <!-- Split Screen -->
        <div class="split-screen">
          <!-- Left Card -->
          <DescriptionTrial />

          <!-- Right Card -->
          <TableTrial />
        </div>
      </v-container>
    </v-main>
  </v-app>
</template>

<script lang="ts" setup>
import DescriptionTrial from "@/components/DescriptionTrial.vue";
import TableTrial from "@/components/TableTrial.vue";
</script>

<style scoped>
/* Split screen container */
.split-screen {
  display: flex;
  justify-content: space-between;
  gap: 16px; /* Space between blocks */
}

/* Individual blocks styling */
.block {
  flex: 1;
  border: solid 2px #4073ff;
  padding: 16px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  text-align: center; /* Center content within the blocks */
}
</style>
