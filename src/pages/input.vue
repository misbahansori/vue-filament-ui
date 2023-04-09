<script setup lang="ts">
import { ref } from "vue";
import InputGroup from "../components/forms/InputGroup.vue";
import Label from "../components/forms/Label.vue";
import TextInput from "../components/forms/TextInput.vue";
import HelperText from "../components/forms/HelperText.vue";

const company = ref("");
</script>

<template>
  <div class="w-full">
    <h2 class="text-2xl font-semibold text-gray-900">Inpus</h2>
    <div class="flex flex-col gap-4 pt-4">
      <div>
        <h3 class="text-lg font-medium text-gray-900">Normal input</h3>
        <div class="pt-2">
          <InputGroup>
            <Label>Company name</Label>
            <TextInput v-model="company" name="company" required />
          </InputGroup>
        </div>
      </div>
      <div>
        <h3 class="text-lg font-medium text-gray-900">
          Normal input with required label
        </h3>
        <div class="pt-2">
          <InputGroup>
            <Label required>Company name</Label>
            <TextInput v-model="company" name="company" required />
          </InputGroup>
        </div>
      </div>
      <div>
        <h3 class="text-lg font-medium text-gray-900">Input with helper</h3>
        <div class="pt-2">
          <InputGroup>
            <Label>Company name</Label>
            <TextInput v-model="company" name="company" required />
            <HelperText>
              This is the name of your company or organization.
            </HelperText>
          </InputGroup>
        </div>
      </div>
      <div>
        <h3 class="text-lg font-medium text-gray-900">
          Input with grid layout
        </h3>
        <div class="grid gap-6 pt-2 lg:grid-cols-2">
          <InputGroup>
            <Label>Company name</Label>
            <TextInput v-model="company" name="company" required />
          </InputGroup>
          <InputGroup>
            <Label>Company name</Label>
            <TextInput v-model="company" name="company" required />
          </InputGroup>
        </div>
      </div>
    </div>
  </div>
</template>
