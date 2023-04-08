<script setup lang="ts">
const props = defineProps<{
  required?: boolean;
}>();
</script>

<template>
  <label
    class="filament-forms-field-wrapper-label inline-flex items-center space-x-3 rtl:space-x-reverse"
    v-bind="$attrs"
  >
    <span class="text-sm font-medium leading-4 text-gray-700">
      <slot />
      <span v-if="props.required" class="whitespace-nowrap">
        <sup class="font-medium text-danger-700">*</sup>
      </span>
    </span>
  </label>
</template>
