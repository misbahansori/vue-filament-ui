<script setup lang="ts">
const props = withDefaults(
  defineProps<{
    inline?: boolean;
  }>(),
  {
    inline: false,
  }
);
</script>

<template>
  <div class="flex gap-2" :class="inline ? 'flex-row' : 'flex-col'">
    <slot />
  </div>
</template>
