<script setup lang="ts">
import Button from "./Components/Button.vue";
import TextInput from "./Components/TextInput.vue";
</script>
<template>
  <div class="min-h-screen px-4 py-12 sm:px-6">
    <div>
      <h1
        class="flex-1 text-2xl font-bold leading-7 text-gray-900 sm:truncate sm:text-3xl"
      >
        Vue Filament UI
      </h1>
      <div class="flex flex-col items-start gap-6 pt-8">
        <div>
          <h2 class="text-lg font-medium text-gray-900">Buttons</h2>
          <div class="flex flex-col gap-3 pt-2">
            <Button>This is a button</Button>
          </div>
        </div>
        <div>
          <h2 class="text-lg font-medium text-gray-900">Text Input</h2>
          <div class="flex flex-col gap-3 pt-2">
            <TextInput />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
