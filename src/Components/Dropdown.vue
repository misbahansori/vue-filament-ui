<script setup lang="ts">
import { Menu, MenuButton, MenuItem, MenuItems } from "@headlessui/vue";
import { useFloating } from "@floating-ui/vue";
import { ref } from "vue";

const reference = ref(null);
const floating = ref(null);
const { x, y, strategy } = useFloating(reference, floating);
</script>

<template>
  <Menu as="div" class="relative inline-block text-left">
    <MenuButton ref="reference">
      <slot />
    </MenuButton>
    <div
      ref="floating"
      class="z-10 w-56 rounded-lg bg-white p-1 shadow-lg ring-1 ring-black/5 transition"
      :style="{
        position: strategy,
        top: `${y ?? 0}px`,
        left: `${x ?? 0}px`,
      }"
    >
      <transition
        enter-active-class="transition ease-out duration-100"
        enter-from-class="transform opacity-0 scale-95"
        enter-to-class="transform opacity-100 scale-100"
        leave-active-class="transition ease-in duration-75"
        leave-from-class="transform opacity-100 scale-100"
        leave-to-class="transform opacity-0 scale-95"
      >
        <MenuItems>
          <slot name="content" />
        </MenuItems>
      </transition>
    </div>
  </Menu>
</template>
