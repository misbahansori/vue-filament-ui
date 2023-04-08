<script setup lang="ts">
import { Menu, MenuButton, MenuItem, MenuItems } from "@headlessui/vue";
</script>

<template>
  <Menu as="div" class="relative inline-block text-left">
    <MenuButton>
      <slot />
    </MenuButton>
    <transition
      enter-active-class="transition ease-out duration-100"
      enter-from-class="transform opacity-0 scale-95"
      enter-to-class="transform opacity-100 scale-100"
      leave-active-class="transition ease-in duration-75"
      leave-from-class="transform opacity-100 scale-100"
      leave-to-class="transform opacity-0 scale-95"
    >
      <MenuItems
        class="absolute z-10 rounded-lg bg-white shadow-lg ring-1 ring-black/5 transition w-56 p-1"
      >
        <slot name="content" />
      </MenuItems>
    </transition>
  </Menu>
</template>
