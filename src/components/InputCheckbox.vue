<template>
  <div class="flex flex-col border p-1 border-gray-300 rounded-md bg-gray-100">
    <span
      v-for="(item, index) in options"
      :key="index"
      class="flex items-center space-x-4"
    >
      <input
        type="checkbox"
        :checked="isChecked(item)"
        :id="item.value"
        :name="item.value"
        :value="item.value"
        @input="handleInput(item, $event)"
      />
      <label :for="item.value">{{ item.name }}</label
      ><br />
    </span>
  </div>
</template>

<script>
export default {
  name: "input-checkbox",

  props: {
    label: {
      type: String,
      default: "label",
      required: false,
    },
    modelValue: {
      type: Array,
      default: () => [],
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
    typeField: {
      type: String,
      required: false,
      default: "select", // select / checkbox
    },
    value: {
      type: Array,
      default: () => [],
      required: true,
    },
  },
  emits: ["update:modelValue"],

  data() {
    return {
      localValues: [],
    };
  },

  created() {
    this.options.forEach((item) => {
      this.localValues[item.value] = this.value.includes(item.value)
        ? true
        : false;
    });
  },

  methods: {
    isChecked(item) {
      return this.value.includes(item.value);
    },

    handleInput(item, event) {
      this.localValues[item.value] = event.target.checked;
      let result = Object.entries(this.localValues)
        .map((item) => {
          if (item[1]) {
            return item[0];
          }
        })
        .filter((item) => item != undefined);
      this.$emit("update:modelValue", result);
    },
  },
};
</script>
