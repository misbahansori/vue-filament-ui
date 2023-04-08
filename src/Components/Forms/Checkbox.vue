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
          <input
            type="checkbox"
            :id="props.name"
            :name="props.name"
            :required="props.required"
            :value="props.modelValue"
            class="filament-forms-checkbox-component rounded border-gray-300 text-primary-600 shadow-sm transition duration-75 focus:border-primary-500 focus:ring-2 focus:ring-primary-500 disabled:opacity-70"
            @input="
              $emit(
                'update:modelValue',
                ($event.target as HTMLInputElement).value
              )
            "
          />
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
