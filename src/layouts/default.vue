<template>
  <div class="min-h-screen bg-gray-100 px-4 py-12 sm:px-6">
    <div class="mx-auto flex max-w-3xl flex-col">
      <h1
        class="flex-1 text-2xl font-bold leading-7 text-gray-900 sm:truncate sm:text-3xl"
      >
        Vue Filament UI
      </h1>
      <nav class="pt-6">
        <ul class="flex flex-wrap items-center gap-4">
          <li>
            <RouterLink to="/button" class="text-blue-600 hover:underline">
              Button
            </RouterLink>
          </li>
          <li>
            <RouterLink to="/input" class="text-blue-600 hover:underline">
              Input
            </RouterLink>
          </li>
          <li>
            <RouterLink to="/checkbox" class="text-blue-600 hover:underline">
              Checkbox
            </RouterLink>
          </li>
          <li>
            <RouterLink to="/toggle" class="text-blue-600 hover:underline">
              Toggle
            </RouterLink>
          </li>
          <li>
            <RouterLink to="/dropdown" class="text-blue-600 hover:underline">
              Dropdown
            </RouterLink>
          </li>
        </ul>
      </nav>
      <div class="flex flex-col items-start gap-6 pt-6">
        <slot />
      </div>
    </div>
  </div>
</template>
