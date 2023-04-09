<script setup lang="ts">
import { Menu, MenuButton, MenuItems } from "@headlessui/vue";
import { Float } from "@headlessui-float/vue";
import { twMerge } from "tailwind-merge";

const props = defineProps<{
  class?: string;
}>();
</script>

<template>
  <Menu>
    <Float flip placement="bottom-start" :offset="6">
      <MenuButton ref="reference">
        <slot />
      </MenuButton>
      <MenuItems
        :class="
          twMerge(
            'z-10 w-56 rounded-lg bg-white p-1 shadow-lg ring-1 ring-black/5',
            props.class
          )
        "
      >
        <slot name="content" />
      </MenuItems>
    </Float>
  </Menu>
</template>
