<template>
  <v-container fluid style="overflow-x: scroll; height: 100%">
    <div class="d-flex justify-space-between">
      <div v-for="(item, i) in data" :key="i">
        <span>
          <span v-if="i % 7 === 0" class="border--week"></span>
          <span class="border--day"></span>
          <span class="day--week">{{ item }}</span>
        </span>
      </div>
    </div>
    <v-divider />
  </v-container>
</template>

<script>
export default {
  name: "CalendarVue",
  data: function () {
    return {
      data: [],
      daysOfWeek: ["S", "M", "T", "W", "T", "F", "S"],
    };
  },
  mounted() {
    this.getDays();
  },
  computed: {
    days() {
      return new Date(
        new Date().getFullYear(),
        new Date().getMonth(),
        0
      ).getDate();
    },
    month() {
      return new Date().getMonth();
    },
    year() {
      return new Date().getFullYear();
    },
  },
  methods: {
    getDays() {
      for (let i = 1; i <= 31; i++) {
        this.data.push(
          this.daysOfWeek[new Date(this.year, this.month, i).getDay()] + i
        );
      }
    },
  },
};
</script>
<style>
.border--week {
  border-left: 1px solid #808b96;
  padding: 0 0 0 0;
  position: relative;
}
.border--day {
  border-left: 1px solid #808b96;
  padding: 0 0 0 10px;
  position: relative;
  top: 97%;
  height: 50vh;
}
.day--week {
  padding: 0 10px 0 0;
}
</style>
