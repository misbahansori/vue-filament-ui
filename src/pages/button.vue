<script setup lang="ts">
import Button from "../components/Button.vue";
</script>
<template>
  <div>
    <h2 class="text-2xl font-semibold text-gray-900">Buttons</h2>
    <div class="flex flex-col gap-4 pt-4">
      <div>
        <h3 class="text-lg font-medium text-gray-900">Small buttons</h3>
        <div class="flex items-start flex-wrap gap-2">
          <Button size="sm" color="primary">Button</Button>
          <Button size="sm" color="secondary">Button</Button>
          <Button size="sm" color="success">Button</Button>
          <Button size="sm" color="warning">Button</Button>
          <Button size="sm" color="gray">Button</Button>
          <Button size="sm" color="danger">Button</Button>
        </div>
      </div>
      <div>
        <h3 class="text-lg font-medium text-gray-900">Medium buttons</h3>
        <div class="flex items-start flex-wrap gap-2">
          <Button size="md" color="primary">Button</Button>
          <Button size="md" color="secondary">Button</Button>
          <Button size="md" color="success">Button</Button>
          <Button size="md" color="warning">Button</Button>
          <Button size="md" color="gray">Button</Button>
          <Button size="md" color="danger">Button</Button>
        </div>
      </div>
      <div>
        <h3 class="text-lg font-medium text-gray-900">Large buttons</h3>
        <div class="flex items-start flex-wrap gap-2">
          <Button size="lg" color="primary">Button</Button>
          <Button size="lg" color="secondary">Button</Button>
          <Button size="lg" color="success">Button</Button>
          <Button size="lg" color="warning">Button</Button>
          <Button size="lg" color="gray">Button</Button>
          <Button size="lg" color="danger">Button</Button>
        </div>
      </div>
      <div>
        <h3 class="text-lg font-medium text-gray-900">Disabled buttons</h3>
        <div class="flex items-start flex-wrap gap-2">
          <Button disabled color="primary">Button</Button>
          <Button disabled color="secondary">Button</Button>
          <Button disabled color="success">Button</Button>
          <Button disabled color="warning">Button</Button>
          <Button disabled color="gray">Button</Button>
          <Button disabled color="danger">Button</Button>
        </div>
      </div>
      <div>
        <h3 class="text-lg font-medium text-gray-900">Outlined button</h3>
        <div class="flex items-start flex-wrap gap-2">
          <Button outlined color="primary">Button</Button>
          <Button outlined color="secondary">Button</Button>
          <Button outlined color="success">Button</Button>
          <Button outlined color="warning">Button</Button>
          <Button outlined color="gray">Button</Button>
          <Button outlined color="danger">Button</Button>
        </div>
      </div>
    </div>
  </div>
</template>
