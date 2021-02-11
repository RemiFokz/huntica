<template>
  <!-- TODO: Реализовать компонент кастомного инпута. Все свойства, события и аттрибуты input должны работать и в CustomInput -->
  <input
    type="text"
    @blur="$emit('blur')"
    @focus="$emit('focus')"
    @input="$emit('input', $event.target.value)"
    @change="$emit('change', $event.target.value)"
    v-bind="$attrs"
    :value="value"
  />
</template>

<script>
export default {
  name: "CustomInput",
  props: {
    value: {
      type: [String, Number],
      default: "",
    },
  },
};
</script>

<style scoped>
</style>
