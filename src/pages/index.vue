<script setup lang="ts">
import { ref } from "vue";
import Button from "../components/Button.vue";
import TextInput from "../components/forms/TextInput.vue";
import TextArea from "../components/forms/TextArea.vue";
import Checkbox from "../components/forms/Checkbox.vue";
import Toggle from "../components/forms/Toggle.vue";
import InputGroup from "../components/forms/InputGroup.vue";
import Label from "../components/forms/Label.vue";
import Dropdown from "../components/Dropdown.vue";
import DropdownItem from "../components/DropdownItem.vue";

const company = ref("");
const isActive = ref(false);
</script>
<template>
  <div class="flex w-full justify-end">
    <h2 class="text-lg font-medium text-gray-900">Dropdown</h2>
    <div class="flex flex-col gap-3 pt-2">
      <Dropdown>
        <Button>Dropdown</Button>
        <template #content>
          <DropdownItem>Helooasd</DropdownItem>
          <DropdownItem>Helooasd</DropdownItem>
          <DropdownItem>Helooasd</DropdownItem>
          <DropdownItem>Helooasd</DropdownItem>
        </template>
      </Dropdown>
    </div>
  </div>
  <div>
    <h2 class="text-lg font-medium text-gray-900">Text Area</h2>
    <div class="flex flex-col gap-3 pt-2">
      <InputGroup>
        <Label :for="company" required>Company name</Label>
        <TextArea v-model="company" name="company" required />
      </InputGroup>
    </div>
  </div>
  <div>
    <h2 class="text-lg font-medium text-gray-900">Toggle</h2>
    <div class="flex flex-col gap-3 pt-2">
      <Toggle v-model="isActive" name="asda" label="Is Active"> </Toggle>

      <Toggle v-model="isActive" name="asda" required> </Toggle>
    </div>
  </div>
  <div class="flex w-full justify-end">
    <h2 class="text-lg font-medium text-gray-900">Dropdown</h2>
    <div class="flex flex-col gap-3 pt-2">
      <Dropdown>
        <Button>Dropdown</Button>
        <template #content>
          <DropdownItem>Helooasd</DropdownItem>
          <DropdownItem>Helooasd</DropdownItem>
          <DropdownItem>Helooasd</DropdownItem>
          <DropdownItem>Helooasd</DropdownItem>
        </template>
      </Dropdown>
    </div>
  </div>
  <div class="flex w-full justify-start">
    <h2 class="text-lg font-medium text-gray-900">Dropdown</h2>
    <div class="flex flex-col gap-3 pt-2">
      <Dropdown class="shadow-2xl">
        <Button>Dropdown</Button>
        <template #content>
          <DropdownItem as="a" href="/logout" class="hover:bg-gray-200">
            Helooasd
          </DropdownItem>
          <DropdownItem>Helooasd</DropdownItem>
          <DropdownItem>Helooasd</DropdownItem>
          <DropdownItem>Helooasd</DropdownItem>
        </template>
      </Dropdown>
    </div>
  </div>
</template>
