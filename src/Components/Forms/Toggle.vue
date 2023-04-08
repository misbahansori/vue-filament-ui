<script setup lang="ts">
import { Switch } from "@headlessui/vue";

const props = withDefaults(
  defineProps<{
    modelValue?: boolean;
  }>(),
  {}
);

const emit = defineEmits<{
  (e: "update:modelValue", value: boolean): void;
}>();
</script>
<template>
  <Switch
    :model-value="modelValue"
    @update:modelValue="emit('update:modelValue', $event)"
    class="relative inline-flex h-6 w-11 shrink-0 cursor-pointer rounded-full border-2 border-transparent outline-none transition-colors duration-150 ease-in-out disabled:pointer-events-none disabled:cursor-not-allowed disabled:opacity-70"
    :class="{
      'bg-primary-600': modelValue,
      'bg-gray-200': !modelValue,
    }"
  >
    <span
      class="pointer-events-none relative inline-block h-5 w-5 transform rounded-full bg-white shadow ring-0 transition duration-150 ease-in-out"
      :class="{
        'translate-x-5 rtl:-translate-x-5': modelValue,
        'translate-x-0': !modelValue,
      }"
    />
  </Switch>
</template>
