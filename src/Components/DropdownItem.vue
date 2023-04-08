<script setup lang="ts">
import { MenuItem } from '@headlessui/vue';
</script>

<template>
  <MenuItem as="div" class="group flex w-full items-center whitespace-nowrap rounded-md p-2 text-sm outline-none hover:bg-gray-50 focus:bg-gray-50">
    <slot/>
  </MenuItem>
</template>
