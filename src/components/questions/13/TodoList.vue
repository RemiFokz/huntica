<template>
  <div class="todo-list">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    type: Array,
    default: () => [],
  },
};
</script>

<style>
.todo-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: stretch;
}
</style>