<script setup lang="ts">
import { ref } from "vue";
import Toggle from "../components/forms/Toggle.vue";

const isActive = ref(false);
</script>

<template>
  <div class="w-full">
    <h2 class="text-2xl font-semibold text-gray-900">Toggle</h2>
    <div class="flex flex-col gap-4 pt-4">
      <div>
        <h3 class="text-lg font-medium text-gray-900">Normal toggle</h3>
        <div class="pt-2">
          <Toggle v-model="isActive" label="Is Active"> </Toggle>
        </div>
      </div>
      <div>
        <h3 class="text-lg font-medium text-gray-900">Inline toggle</h3>
        <div class="pt-2">
          <Toggle v-model="isActive" label="Is Active" inline required>
          </Toggle>
        </div>
      </div>
    </div>
  </div>
</template>
