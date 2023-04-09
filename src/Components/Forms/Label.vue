<script setup lang="ts">
import { twMerge } from "tailwind-merge";

const props = defineProps<{
  required?: boolean;
  class?: string;
}>();
</script>

<template>
  <label
    :class="
      twMerge(
        'items-center text-sm font-medium leading-4 text-gray-700',
        props.class
      )
    "
    v-bind="$attrs"
  >
    <slot />
    <span v-if="props.required" class="whitespace-nowrap">
      <sup class="font-medium text-danger-700">*</sup>
    </span>
  </label>
</template>
