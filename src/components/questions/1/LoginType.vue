<template>
  <!-- TODO: При переключении типа логина, введенные значения должны очищаться -->
  <div>
    <template>
      <label>{{ text.label }}</label>
      <input v-model="login" :placeholder="`Enter your ${text.label}`" />
    </template>
    <button @click="switchMethod">Change login type</button>
  </div>
</template>

<script>
export default {
  name: "LoginType",
  data() {
    return {
      loginType: "phone",
      login: "",
    };
  },
  computed: {
    text() {
      switch (this.loginType) {
        case "phone":
          return {
            label: "phone",
          };
        default:
          return {
            label: "login",
          };
      }
    },
  },
  methods: {
    switchMethod() {
      this.login = "";
      this.loginType = this.loginType === "phone" ? "email" : "phone";
    },
  },
};
</script>

<style scoped>
label {
  text-transform: capitalize;
}
</style>
