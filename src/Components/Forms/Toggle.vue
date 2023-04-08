<script setup lang="ts">
import { ref, watchEffect } from "vue";
import Label from "./Label.vue";
import { Switch } from "@headlessui/vue";

const props = withDefaults(
  defineProps<{
    name: string;
    modelValue?: boolean;
    required?: boolean;
    label?: string | false;
    inline?: boolean;
  }>(),
  {
    required: false,
    type: "text",
  }
);

const emit = defineEmits<{
  (e: "update:modelValue", value: boolean): void;
}>();
</script>
<template>
  <div class="filament-forms-field-wrapper">
    <div class="space-y-2">
      <div
        v-if="!inline"
        class="flex items-center justify-between space-x-2 rtl:space-x-reverse"
      >
        <Label
          :required="props.required"
          :label="props.label !== false ? props.label : props.name || ''"
          :for="props.name"
        />
      </div>
      <div
        class="flex items-center justify-between space-x-2 rtl:space-x-reverse"
      >
        <component
          :is="inline ? 'label' : 'div'"
          class="filament-forms-text-input-component group flex items-center space-x-2 rtl:space-x-reverse"
        >
          <Switch
            :model-value="modelValue"
            @update:modelValue="emit('update:modelValue', $event)"
            class="filament-forms-toggle-component relative inline-flex h-6 w-11 shrink-0 cursor-pointer rounded-full border-2 border-transparent bg-primary-600 outline-none transition-colors duration-200 ease-in-out disabled:pointer-events-none disabled:cursor-not-allowed disabled:opacity-70"
            :class="{
              'bg-primary-600': modelValue,
              'bg-gray-200': !modelValue,
            }"
          >
            <span class="sr-only">Enable notifications</span>
            <span
              class="pointer-events-none relative inline-block h-5 w-5 translate-x-5 transform rounded-full bg-white shadow ring-0 transition duration-200 ease-in-out rtl:-translate-x-5"
              :class="{
                'translate-x-5 rtl:-translate-x-5': modelValue,
                'translate-x-0': !modelValue,
              }"
            />
          </Switch>

          <Label
            v-if="inline"
            :required="props.required"
            :label="props.label !== false ? props.label : props.name || ''"
            :for="props.name"
          >
          </Label>
        </component>
      </div>
    </div>
  </div>
</template>
