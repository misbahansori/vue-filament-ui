<script setup lang="ts">
import { twMerge } from "tailwind-merge";

const props = withDefaults(
  defineProps<{
    modelValue?: string;
    class?: string;
  }>(),
  {}
);

const emit = defineEmits<{
  (e: "update:modelValue", value: boolean): void;
}>();
</script>

<template>
  <input
    type="checkbox"
    :value="props.modelValue"
    :class="
      twMerge(
        'rounded border-gray-300 text-primary-600 shadow-sm transition duration-75 focus:border-primary-500 focus:ring-2 focus:ring-primary-500 disabled:opacity-70',
        props.class
      )
    "
    @input="
      $emit('update:modelValue', ($event.target as HTMLInputElement).value)
    "
  />
</template>
