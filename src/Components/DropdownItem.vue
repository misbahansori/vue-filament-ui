<script setup lang="ts">
import { MenuItem } from '@headlessui/vue';

const props = withDefaults(defineProps<{
  as?: string;
}>(), {
  as: 'div',
});
</script>

<template>
  <MenuItem :as="props.as" class="group flex w-full items-center whitespace-nowrap rounded-md p-2 text-sm outline-none hover:bg-gray-50 focus:bg-gray-50">
    <slot/>
  </MenuItem>
</template>
