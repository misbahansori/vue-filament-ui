<script setup lang="ts">
const props = withDefaults(
  defineProps<{
    required: boolean;
    label?: string;
    for: string;
  }>(),
  {
    required: false,
  }
);
</script>

<template>
  <label
    v-if="props.label"
    class="filament-forms-field-wrapper-label inline-flex items-center space-x-3 rtl:space-x-reverse"
    :for="props.for"
  >
    <span class="text-sm font-medium leading-4 text-gray-700">
      {{ props.label[0].toUpperCase() + props.label.slice(1) }}
      <span v-if="props.required" class="whitespace-nowrap">
        <sup class="font-medium text-danger-700">*</sup>
      </span>
    </span>
  </label>
</template>
