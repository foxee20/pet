<template>
  <input :value="modelValue" @input="onInput" />
</template>

<script setup>
defineProps(["modelValue"]);
const emit = defineEmits(["update:modelValue"]);

function onInput(event) {
  emit("update:modelValue", event.target.value);
}
name: "default_input";
</script>

<style lang="scss" scoped>
.field {
  border: 1px solid #363a3d;
  font-size: 16px;
  padding: 0px 16px;
  font-style: normal;
  font-weight: 500;
  line-height: 150%;
  letter-spacing: 0.15px;
  border-radius: 8px;
  color: #fff;
  background-color: #1a1d21;
}
</style>
