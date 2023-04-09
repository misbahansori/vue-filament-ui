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
  <div>
    <h2 class="text-lg font-medium text-gray-900">Buttons</h2>
    <div class="grid grid-cols-6 gap-2">
      <Button size="sm" color="primary">Button</Button>
      <Button size="sm" color="secondary">Button</Button>
      <Button size="sm" color="success">Button</Button>
      <Button size="sm" color="warning">Button</Button>
      <Button size="sm" color="gray">Button</Button>
      <Button size="sm" color="danger">Button</Button>
      <Button size="md" color="primary">Button</Button>
      <Button size="md" color="secondary">Button</Button>
      <Button size="md" color="success">Button</Button>
      <Button size="md" color="warning">Button</Button>
      <Button size="md" color="gray">Button</Button>
      <Button size="md" color="danger">Button</Button>
      <Button size="lg" color="primary">Button</Button>
      <Button size="lg" color="secondary">Button</Button>
      <Button size="lg" color="success">Button</Button>
      <Button size="lg" color="warning">Button</Button>
      <Button size="lg" color="gray">Button</Button>
      <Button size="lg" color="danger">Button</Button>
      <Button disabled color="primary">Button</Button>
      <Button disabled color="secondary">Button</Button>
      <Button disabled color="success">Button</Button>
      <Button disabled color="warning">Button</Button>
      <Button disabled color="gray">Button</Button>
      <Button disabled color="danger">Button</Button>
      <Button outlined color="primary">Button</Button>
      <Button outlined color="secondary">Button</Button>
      <Button outlined color="success">Button</Button>
      <Button outlined color="warning">Button</Button>
      <Button outlined color="gray">Button</Button>
      <Button outlined color="danger">Button</Button>
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
  <div>
    <h2 class="text-lg font-medium text-gray-900">Text Input</h2>
    <div class="flex flex-col gap-3 pt-2">
      <InputGroup>
        <Label :for="company" required>Company name</Label>
        <TextInput v-model="company" name="company" required />
      </InputGroup>
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
    <h2 class="text-lg font-medium text-gray-900">Checkbox</h2>
    <div class="flex flex-col gap-3 pt-2">
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
