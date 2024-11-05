<template>
  <div class="flex flex-col border p-1 border-gray-300 rounded-md bg-gray-100">
    <label :for="uid" class="text-sm font-medium mb-2">{{ label }}</label>
    <div class="border bg-white border-gray-300 rounded-md px-2">
      <input
        v-if="typeField === 'email'"
        :id="uid"
        class="w-full bg-transparent focus:outline-none"
        type="email"
        placeholder="john.doe@testmail.com"
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
      />
      <input
        v-if="typeField === 'text'"
        :id="uid"
        class="w-full bg-transparent focus:outline-none"
        type="text"
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
      />
      <input
        v-if="typeField === 'number'"
        :id="uid"
        class="w-full bg-transparent focus:outline-none"
        type="number"
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "input-text",
  props: {
    label: {
      type: String,
      default: "label",
      required: false,
    },
    modelValue: {
      type: String,
      default: "",
      required: true,
    },
    uid: {
      type: String,
      required: true,
    },
    isTypeEmail: {
      type: Boolean,
      required: false,
      default: false,
    },
    typeField: {
      type: String,
      required: false,
      default: "text", // text, email, number
    },
  },
  emits: ["update:modelValue"],
};
</script>
