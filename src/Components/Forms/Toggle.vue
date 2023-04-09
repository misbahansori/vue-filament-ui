<script setup lang="ts">
import { Switch, SwitchGroup, SwitchLabel } from "@headlessui/vue";
import Label from "./Label.vue";

const props = withDefaults(
  defineProps<{
    modelValue?: boolean;
    inline?: boolean;
    label?: string;
    required?: boolean;
  }>(),
  {
    inline: false,
    required: false,
  }
);

const emit = defineEmits<{
  (e: "update:modelValue", value: boolean): void;
}>();
</script>
<template>
  <SwitchGroup
    as="div"
    class="flex gap-2"
    :class="{
      'flex-row items-center': !props.inline,
      'flex-col': props.inline,
    }"
  >
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
    <SwitchLabel :as="Label" :required="props.required">
      {{ props.label }}
    </SwitchLabel>
  </SwitchGroup>
</template>
