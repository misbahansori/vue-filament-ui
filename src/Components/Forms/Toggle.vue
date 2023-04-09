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
  <SwitchGroup>
    <div
      class="flex gap-2"
      :class="{
        'flex-row items-center': !props.inline,
        'flex-col-reverse': props.inline,
      }"
    >
      <Switch
        :model-value="props.modelValue"
        @update:model-value="$emit('update:modelValue', $event)"
        :class="[
          props.modelValue ? 'bg-indigo-600' : 'bg-gray-200',
          'relative inline-flex h-6 w-11 flex-shrink-0 cursor-pointer rounded-full border-2 border-transparent transition-colors duration-200 ease-in-out focus:outline-none focus:ring-2 focus:ring-indigo-600 focus:ring-offset-2',
        ]"
      >
        <span class="sr-only">Use setting</span>
        <span
          aria-hidden="true"
          :class="[
            props.modelValue ? 'translate-x-5' : 'translate-x-0',
            'pointer-events-none inline-block h-5 w-5 transform rounded-full bg-white shadow ring-0 transition duration-200 ease-in-out',
          ]"
        />
      </Switch>
      <SwitchLabel :as="Label" :required="props.required">
        {{ props.label }}
      </SwitchLabel>
    </div>
  </SwitchGroup>
</template>
