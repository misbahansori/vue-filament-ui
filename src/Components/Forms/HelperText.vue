<script setup lang="ts">
import { twMerge } from "tailwind-merge";

const props = defineProps<{
  class?: string;
}>();
</script>

<template>
  <p :class="twMerge('text-sm text-gray-600', props.class)">
    <slot />
  </p>
</template>
