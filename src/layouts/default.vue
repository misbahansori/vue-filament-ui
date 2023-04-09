<template>
  <div class="min-h-screen bg-gray-100 px-4 py-12 sm:px-6">
    <div class="flex flex-col mx-auto max-w-xl">
      <h1
        class="flex-1 text-2xl font-bold leading-7 text-gray-900 sm:truncate sm:text-3xl"
      >
        Vue Filament UI
      </h1>
      <div class="flex flex-col items-start gap-6 pt-8">
        <slot />
      </div>
    </div>
  </div>
</template>
