<script setup lang="ts">
const props = defineProps<{
  required?: boolean;
}>();
</script>

<template>
  <label
    class="inline-flex items-center space-x-3 text-sm font-medium leading-4 text-gray-700 rtl:space-x-reverse"
    v-bind="$attrs"
  >
    <slot />
    <span v-if="props.required" class="whitespace-nowrap">
      <sup class="font-medium text-danger-700">*</sup>
    </span>
  </label>
</template>
