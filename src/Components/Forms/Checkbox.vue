<script setup lang="ts">
import Label from "./Label.vue";

const props = withDefaults(
  defineProps<{
    name: string;
    modelValue?: string;
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
  <input
    type="checkbox"
    :id="props.name"
    :name="props.name"
    :required="props.required"
    :value="props.modelValue"
    class="filament-forms-checkbox-component rounded border-gray-300 text-primary-600 shadow-sm transition duration-75 focus:border-primary-500 focus:ring-2 focus:ring-primary-500 disabled:opacity-70"
    @input="
      $emit('update:modelValue', ($event.target as HTMLInputElement).value)
    "
  />
</template>
