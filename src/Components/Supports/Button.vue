<script setup lang="ts">
import { cva, type VariantProps } from "class-variance-authority";
const button = cva("button", {
  variants: {
    color: {
      primary: [],
      success: [],
      danger: [],
      warning: [],
      gray: [],
      secondary: [],
    },
    size: {
      sm: ["min-h-[2rem]", "px-3", "text-sm"],
      md: ["min-h-[2.25rem]", "px-3", "text-sm"],
      lg: ["min-h-[2.75rem]", "px-6", "text-lg"],
    },
    outlined: {
      true: ["border"],
      false: [],
    },
  },
  compoundVariants: [
    {
      color: "primary",
      outlined: true,
      class: [
        "shadow",
        "focus:ring-white",
        "border-primary-600",
        "text-primary-600",
        "hover:bg-primary-600/20",
        "focus:bg-primary-700/20",
        "focus:ring-offset-primary-700",
      ],
    },
    {
      color: "success",
      outlined: true,
      class: [
        "shadow",
        "focus:ring-white",
        "border-success-600",
        "text-success-600",
        "hover:bg-success-600/20",
        "focus:bg-success-700/20",
        "focus:ring-offset-success-700",
      ],
    },
    {
      color: "danger",
      outlined: true,
      class: [
        "shadow",
        "focus:ring-white",
        "border-danger-600",
        "text-danger-600",
        "hover:bg-danger-600/20",
        "focus:bg-danger-700/20",
        "focus:ring-offset-danger-700",
      ],
    },
    {
      color: "warning",
      outlined: true,
      class: [
        "shadow",
        "focus:ring-white",
        "border-warning-600",
        "text-warning-600",
        "hover:bg-warning-600/20",
        "focus:bg-warning-700/20",
        "focus:ring-offset-warning-700",
      ],
    },
    {
      color: "gray",
      outlined: true,
      class: [
        "shadow",
        "focus:ring-white",
        "border-gray-600",
        "text-gray-600",
        "hover:bg-gray-600/20",
        "focus:bg-gray-700/20",
        "focus:ring-offset-gray-700",
      ],
    },
    {
      color: "secondary",
      outlined: true,
      class: [
        "shadow",
        "focus:ring-white",
        "border-gray-300",
        "text-gray-800",
        "hover:bg-gray-50 focus",
        "border-primary-600 focus:bg",
        "primary-50 focus:text-primary-600 focus:ring-primary-600",
      ],
    },
    {
      color: "primary",
      outlined: false,
      class: [
        "border-transparent",
        "text-white",
        "shadow",
        "focus:ring-white",
        "bg-primary-600",
        "hover:bg-primary-500",
        "focus:bg-primary-700",
        "focus:ring-offset-primary-700",
      ],
    },
    {
      color: "success",
      outlined: false,
      class: [
        "border-transparent",
        "text-white",
        "shadow",
        "focus:ring-white",
        "bg-success-600",
        "hover:bg-success-500",
        "focus:bg-success-700",
        "focus:ring-offset-success-700",
      ],
    },
    {
      color: "danger",
      outlined: false,
      class: [
        "border-transparent",
        "text-white",
        "shadow",
        "focus:ring-white",
        "bg-danger-600",
        "hover:bg-danger-500",
        "focus:bg-danger-700",
        "focus:ring-offset-danger-700",
      ],
    },
    {
      color: "warning",
      outlined: false,
      class: [
        "border-transparent",
        "text-white",
        "shadow",
        "focus:ring-white",
        "bg-warning-600",
        "hover:bg-warning-500",
        "focus:bg-warning-700",
        "focus:ring-offset-warning-700",
      ],
    },
    {
      color: "gray",
      outlined: false,
      class: [
        "border-transparent",
        "text-white",
        "shadow",
        "focus:ring-white",
        "bg-gray-600",
        "hover:bg-gray-500",
        "focus:bg-gray-700",
        "focus:ring-offset-gray-700",
      ],
    },
    {
      color: "secondary",
      outlined: false,
      class: [
        "border-gray-300",
        "bg-white",
        "text-gray-800",
        "shadow",
        "focus:ring-white",
        "hover:bg-gray-50",
        "focus:border-primary-600",
        "focus:bg-primary-50",
        "focus:text-primary-600",
        "focus:ring-primary-600",
      ],
    },
  ],
  defaultVariants: {
    size: "md",
    outlined: false,
  },
});

type ButtonProps = Required<VariantProps<typeof button>>;

const props = withDefaults(
  defineProps<{
    color?: ButtonProps["color"];
    size?: ButtonProps["size"];
    type?: "button" | "submit" | "reset";
    outlined?: ButtonProps["outlined"];
    disabled?: boolean;
    tag?: string;
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
  <component
    :is="props.tag"
    :type="props.type"
    :disabled="props.disabled"
    class="filament-button filament-button-size-md inline-flex items-center justify-center gap-1 rounded-lg border py-1 font-medium outline-none transition-colors focus:ring-2 focus:ring-inset focus:ring-offset-2"
    :class="button(props)"
  >
    <slot />
  </component>
</template>
