<template>
  <div>
    <!-- FIXME: При первичном рендере компонента все ок. Но при вводе числа, компонент все равно выдает ошибку -->
    <span v-if="!isNum()" style="color: red">Вы ввели не число</span><br />
    <input v-model="value" />
    {{ value }}
  </div>
</template>

<script>
export default {
  name: "WrongType",
  data() {
    return {
      value: 1,
    };
  },
  methods: {
    isNum() {
      return Number.isInteger(parseInt(this.value, 10));
    },
  },
};
</script>

<style scoped>
</style>
