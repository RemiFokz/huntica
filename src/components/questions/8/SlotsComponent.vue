<template>
  <div>
    <SlotsComponentUser>
      <!-- FIXME: при переопределении слота, username не отображается -->
      <template scope="props">
        <span>Login: {{ props.username }}</span>
      </template>
    </SlotsComponentUser>
  </div>
</template>

<script>
import SlotsComponentUser from "@/components/questions/8/SlotsComponentUser";
export default {
  name: "SlotsComponent",
  components: { SlotsComponentUser },
};
</script>

<style scoped>
</style>
