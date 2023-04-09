<script setup lang="ts">
import { ref } from "vue";
import InputGroup from "../components/forms/InputGroup.vue";
import Label from "../components/forms/Label.vue";
import TextInput from "../components/forms/TextInput.vue";
import HelperText from "../components/forms/HelperText.vue";
import Checkbox from "../components/forms/Checkbox.vue";

const company = ref("");
</script>

<template>
  <div class="w-full">
    <h2 class="text-2xl font-semibold text-gray-900">Checkbox</h2>
    <div class="flex flex-col gap-4 pt-4">
      <div>
        <h3 class="text-lg font-medium text-gray-900">Normal input</h3>
        <div class="pt-2">
          <InputGroup>
            <Label :for="company" required>Company name</Label>
            <Checkbox name="company" required />
          </InputGroup>
          <InputGroup inline>
            <Checkbox inline name="name" required />
            <Label for="name" required>Company name</Label>
          </InputGroup>
        </div>
      </div>
    </div>
  </div>
</template>
