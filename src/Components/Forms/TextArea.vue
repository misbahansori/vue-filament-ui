<script setup lang="ts">
import Label from "./Label.vue";

const props = withDefaults(
  defineProps<{
    name: string;
    modelValue?: string;
    required?: boolean;
    label?: string | false;
    rows?: number;
  }>(),
  {
    required: false,
    type: "text",
  }
);

const emit = defineEmits<{
  (e: "update:modelValue", value: string): void;
}>();
</script>
<template>
  <textarea
    :value="props.modelValue"
    @input="
      $emit('update:modelValue', ($event.target as HTMLInputElement).value)
    "
    :type="props.type"
    :name="props.name"
    :required="props.required"
    :rows="props.rows"
    class="block w-full rounded-lg border-gray-300 shadow-sm outline-none transition duration-75 focus:border-primary-500 focus:ring-1 focus:ring-inset focus:ring-primary-500 disabled:opacity-70"
  />
</template>
