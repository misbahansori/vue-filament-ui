<template>
  <div class="filament-forms-field-wrapper">
    <div class="space-y-2">
      <div
        class="flex items-center justify-between space-x-2 rtl:space-x-reverse"
      >
        <label
          class="filament-forms-field-wrapper-label inline-flex items-center space-x-3 rtl:space-x-reverse"
          for="data.name"
        >
          <span class="text-sm font-medium leading-4 text-gray-700">
            Company Name<span class="whitespace-nowrap">
              <sup class="font-medium text-danger-700">*</sup>
            </span>
          </span>
        </label>
      </div>

      <div
        class="filament-forms-text-input-component group flex items-center space-x-2 rtl:space-x-reverse"
      >
        <div class="flex-1">
          <input
            type="text"
            class="block w-full rounded-lg border-gray-300 shadow-sm outline-none transition duration-75 focus:border-primary-500 focus:ring-1 focus:ring-inset focus:ring-primary-500 disabled:opacity-70"
          />
        </div>
      </div>
    </div>
  </div>
</template>
