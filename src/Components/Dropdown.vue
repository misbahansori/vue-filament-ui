<script setup lang="ts">
import { Menu, MenuButton, MenuItems } from "@headlessui/vue";
import { Float } from "@headlessui-float/vue";
</script>

<template>
  <Menu as="div" class="inline-block text-left" v-slot="{ open }">
    <Float flip placement="bottom-start" :offset="6">
      <MenuButton ref="reference">
        <slot />
      </MenuButton>
      <MenuItems
        class="z-10 w-56 rounded-lg bg-white p-1 shadow-lg ring-1 ring-black/5"
      >
        <slot name="content" />
      </MenuItems>
    </Float>
  </Menu>
</template>
