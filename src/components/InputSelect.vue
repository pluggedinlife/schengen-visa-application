<template>
  <div class="flex flex-col border p-1 border-gray-300 rounded-md bg-gray-100">
    <label :for="uid" class="text-sm font-medium mb-2">{{ label }}</label>
    <div class="border bg-white border-gray-300 rounded-md px-2">
      <select
        :name="name"
        :id="uid"
        @input="$emit('update:modelValue', $event.target.value)"
        :value="modelValue"
      >
        <option
          v-for="(item, index) in options"
          :key="index"
          :value="item.value"
        >
          {{ item.name }}
        </option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: "input-select",
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
    name: {
      type: String,
      required: true,
    },
    options: {
      type: Array,
      default: () => [{ name: "Empty", value: "empty" }],
      required: true,
    },
  },
  emits: ["update:modelValue"],
};
</script>
