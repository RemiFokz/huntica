<template>
  <header class="header">
    <nav class="header-nav" />
    <div class="container">
      <h1>{{ title }}</h1>
    </div>
  </header>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      default: "My todo list",
    },
  },
};
</script>
<style scoped>
.header {
  width: 100%;
}

.header-nav {
  background: teal;
  width: 100%;
  height: 56px;
}
</style>