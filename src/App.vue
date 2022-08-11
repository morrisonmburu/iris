<template>
  <v-app id="inspire">
    <v-main>
      <Calendar />
    </v-main>
  </v-app>
</template>

<script>
import Calendar from "./components/Calendar.vue";

export default {
  name: "App",

  components: {
    Calendar,
  },

  data: () => ({
    //
  }),
};
</script>
