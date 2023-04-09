<script setup lang="ts">
import { twMerge } from "tailwind-merge";

const props = withDefaults(
  defineProps<{
    class?: string;
  }>(),
  {}
);
</script>

<template>
  <div :class="twMerge('flex gap-2', props.class)">
    <slot />
  </div>
</template>
