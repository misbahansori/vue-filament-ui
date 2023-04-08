<script setup lang="ts">
const props = withDefaults(
  defineProps<{
    color?: "primary" | "secondary" | "success" | "warning" | "gray" | "danger";
    size?: "sm" | "md" | "lg";
    type?: "button" | "submit" | "reset";
    outlined?: boolean;
    disabled?: boolean;
    tag: string;
  }>(),
  {
    color: "primary",
    size: "md",
    type: "button",
    outlined: false,
    disabled: false,
    tag: "button",
  }
);
</script>

<template>
  <!-- @php
    $buttonClasses = array_merge([
        "filament-button filament-button-size-{$size} inline-flex items-center justify-center py-1 gap-1 font-medium rounded-lg border transition-colors outline-none focus:ring-offset-2 focus:ring-2 focus:ring-inset",
        'opacity-70 cursor-not-allowed pointer-events-none' => $disabled,
        'min-h-[2.25rem] px-4 text-sm' => $size === 'md',
        'min-h-[2rem] px-3 text-sm' => $size === 'sm',
        'min-h-[2.75rem] px-6 text-lg' => $size === 'lg',
    ], $outlined ? [
        'shadow focus:ring-white' => $color !== 'secondary',
        'text-primary-600 border-primary-600 hover:bg-primary-600/20 focus:bg-primary-700/20 focus:ring-offset-primary-700' => $color === 'primary',
        'text-success-600 border-success-600 hover:bg-success-600/20 focus:bg-success-700/20 focus:ring-offset-success-700' => $color === 'success',
        'text-danger-600 border-danger-600 hover:bg-danger-600/20 focus:bg-danger-700/20 focus:ring-offset-danger-700' => $color === 'danger',
        'text-warning-600 border-warning-600 hover:bg-warning-600/20 focus:bg-warning-700/20 focus:ring-offset-warning-700' => $color === 'warning',
        'text-gray-600 border-gray-600 hover:bg-gray-600/20 focus:bg-gray-700/20 focus:ring-offset-gray-700' => $color === 'gray',
        'text-gray-800 border-gray-300 hover:bg-gray-50 focus:ring-primary-600 focus:text-primary-600 focus:bg-primary-50 focus:border-primary-600' => $color === 'secondary',
    ] : [
        'text-white shadow focus:ring-white border-transparent' => $color !== 'secondary',
        'bg-primary-600 hover:bg-primary-500 focus:bg-primary-700 focus:ring-offset-primary-700' => $color === 'primary',
        'bg-success-600 hover:bg-success-500 focus:bg-success-700 focus:ring-offset-success-700' => $color === 'success',
        'bg-danger-600 hover:bg-danger-500 focus:bg-danger-700 focus:ring-offset-danger-700' => $color === 'danger',
        'bg-warning-600 hover:bg-warning-500 focus:bg-warning-700 focus:ring-offset-warning-700' => $color === 'warning',
        'bg-gray-600 hover:bg-gray-500 focus:bg-gray-700 focus:ring-offset-gray-700' => $color === 'gray',
        'text-gray-800 bg-white border-gray-300 hover:bg-gray-50 focus:ring-primary-600 focus:text-primary-600 focus:bg-primary-50 focus:border-primary-600' => $color === 'secondary',
    ]);

    $iconClasses = \Illuminate\Support\Arr::toCssClasses([
        'filament-button-icon',
        'w-4 h-4' => $size === 'sm',
        'w-5 h-5' => $size === 'md',
        'w-6 h-6' => $size === 'lg',
    ]);
@endphp -->
  <button
    :type="props.type"
    :disabled="props.disabled"
    class="filament-button filament-button-size-md inline-flex items-center justify-center gap-1 rounded-lg border py-1 font-medium outline-none transition-colors focus:ring-2 focus:ring-inset focus:ring-offset-2"
    :class="[
      {
        'pointer-events-none cursor-not-allowed opacity-70': props.disabled,
        'min-h-[2.25rem] px-4 text-sm': props.size === 'md',
        'min-h-[2rem] px-3 text-sm': props.size === 'sm',
        'min-h-[2.75rem] px-6 text-lg': props.size === 'lg',
      },
      props.outlined
        ? {
            'shadow focus:ring-white': props.color !== 'secondary',
            'border-primary-600 text-primary-600 hover:bg-primary-600/20 focus:bg-primary-700/20 focus:ring-offset-primary-700':
              props.color === 'primary',
            'border-success-600 text-success-600 hover:bg-success-600/20 focus:bg-success-700/20 focus:ring-offset-success-700':
              props.color === 'success',
            'border-danger-600 text-danger-600 hover:bg-danger-600/20 focus:bg-danger-700/20 focus:ring-offset-danger-700':
              props.color === 'danger',
            'border-warning-600 text-warning-600 hover:bg-warning-600/20 focus:bg-warning-700/20 focus:ring-offset-warning-700':
              props.color === 'warning',
            'border-gray-600 text-gray-600 hover:bg-gray-600/20 focus:bg-gray-700/20 focus:ring-offset-gray-700':
              props.color === 'gray',
            'border-gray-300 text-gray-800 hover:bg-gray-50 focus:border-primary-600 focus:bg-primary-50 focus:text-primary-600 focus:ring-primary-600':
              props.color === 'secondary',
          }
        : {
            'border-transparent text-white shadow focus:ring-white':
              props.color !== 'secondary',
            'bg-primary-600 hover:bg-primary-500 focus:bg-primary-700 focus:ring-offset-primary-700':
              props.color === 'primary',
            'bg-success-600 hover:bg-success-500 focus:bg-success-700 focus:ring-offset-success-700':
              props.color === 'success',
            'bg-danger-600 hover:bg-danger-500 focus:bg-danger-700 focus:ring-offset-danger-700':
              props.color === 'danger',
            'bg-warning-600 hover:bg-warning-500 focus:bg-warning-700 focus:ring-offset-warning-700':
              props.color === 'warning',
            'bg-gray-600 hover:bg-gray-500 focus:bg-gray-700 focus:ring-offset-gray-700':
              props.color === 'gray',
            'border-gray-300 bg-white text-gray-800 hover:bg-gray-50 focus:border-primary-600 focus:bg-primary-50 focus:text-primary-600 focus:ring-primary-600':
              props.color === 'secondary',
          },
    ]"
  >
    <slot />
  </button>
</template>
