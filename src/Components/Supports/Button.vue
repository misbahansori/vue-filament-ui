<script setup lang="ts">
import { cva, type VariantProps } from "class-variance-authority";
import { twMerge } from "tailwind-merge";

const buttonVariants = cva(
  [
    "inline-flex",
    "items-center",
    "justify-center",
    "gap-1",
    "rounded-lg",
    "border",
    "py-1",
    "font-medium",
    "outline-none",
    "transition-colors",
    "focus:ring-2",
    "focus:ring-white",
    "focus:ring-inset",
    "focus:ring-offset-2",
    "shadow",
  ],
  {
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
        false: ["border-transparent", "text-white"],
      },
      disabled: {
        true: ["opacity-70", "cursor-not-allowed", "pointer-events-none"],
        false: [],
      },
    },
    compoundVariants: [
      {
        color: "primary",
        outlined: true,
        class: [
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
  }
);

type ButtonProps = Required<VariantProps<typeof buttonVariants>>;

const props = withDefaults(
  defineProps<{
    color?: ButtonProps["color"];
    size?: ButtonProps["size"];
    outlined?: boolean;
    type?: "button" | "submit" | "reset";
    disabled?: boolean;
    tag?: string;
    class?: string;
  }>(),
  {
    outlined: false,
    type: "button",
    disabled: false,
    tag: "button",
    class: "",
  }
);
</script>

<template>
  <component
    :is="props.tag"
    :type="props.type"
    :disabled="props.disabled"
    :class="twMerge(buttonVariants(props), props.class)"
  >
    <slot />
  </component>
</template>
