<template>
  <div>
    <ul>
      <!-- FIXME: Vue не рекомендует использовать одновременно v-for и v-if, необходимо внести изменения-->
      <li v-for="user in users" :key="user.id">
        {{ user.name }}
      </li>
      {{
        users
      }}
    </ul>
  </div>
</template>

<script>
export default {
  name: "UsersListVFor",
  computed: {
    users() {
      return [
        {
          id: 1,
          name: "Nagibator2005",
          isActive: true,
        },
        {
          id: 2,
          name: "Nagibator2006",
          isActive: false,
        },
      ].filter(({ isActive }) => isActive);
    },
  },
};
</script>

<style scoped>
</style>
