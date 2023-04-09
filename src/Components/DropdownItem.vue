<script setup lang="ts">
import { MenuItem } from "@headlessui/vue";
import { twMerge } from "tailwind-merge";

const props = withDefaults(
  defineProps<{
    as?: string;
    class?: string;
  }>(),
  {
    as: "div",
  }
);
</script>

<template>
  <MenuItem
    :as="props.as"
    :class="
      twMerge(
        'group flex w-full items-center whitespace-nowrap rounded-md p-2 text-sm outline-none hover:bg-gray-100 focus:bg-gray-100',
        props.class
      )
    "
  >
    <slot />
  </MenuItem>
</template>
