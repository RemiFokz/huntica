<template>
  <div>
    <input
      @input="$emit('inputPhone', $event.target.value)"
      :value="phone"
      class="phone"
      placeholder="phone"
    />
    <span v-if="error">Не правильно введен номер телефона</span>
  </div>
</template>

<script>
// TODO: реализовать валидацию входных данных свойства и валидацию input - тип телефон, вида
const regexp = /^((\+7|7|8)+([0-9]){10})$/;
export default {
  name: "PhoneValidation",
  props: {
    phone: {},
  },
  data() {
    return {
      error: Boolean,
    };
  },
  watch: {
    phone: {
      immediate: true,
      handler(newVal) {
        this.error = !regexp.test(newVal);
      },
    },
  },
};
</script>

<style scoped>
.error {
  color: red;
}
</style>
