<script setup lang="ts">
import { ref } from "vue";
import Button from "../Components/Button.vue";
import TextInput from "../Components/Forms/TextInput.vue";
import TextArea from "../Components/Forms/TextArea.vue";
import Checkbox from "../Components/Forms/Checkbox.vue";
import Toggle from "../Components/Forms/Toggle.vue";
import InputGroup from "../Components/Forms/InputGroup.vue";
import Label from "../Components/Forms/Label.vue";
import Dropdown from "../Components/Dropdown.vue";
import DropdownItem from "../Components/DropdownItem.vue";

const company = ref("");
const isActive = ref(false);
</script>
<template>
  <div class="min-h-screen bg-gray-100 px-4 py-12 sm:px-6">
    <div class="flex flex-col mx-auto max-w-xl">
      <h1
        class="flex-1 text-2xl font-bold leading-7 text-gray-900 sm:truncate sm:text-3xl"
      >
        Vue Filament UI
      </h1>
    </div>
  </div>
</template>
