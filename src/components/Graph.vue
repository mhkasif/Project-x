<template>
  <div id="graph">
    <apexchart
      width="500"
      type="line"
      v-bind:options="options"
      v-bind:series="series"

    ></apexchart>
  </div>
</template>

<script>
import VueApexCharts from "vue-apexcharts";
import Vue from "vue";

Vue.component("apexchart", VueApexCharts);
export default {
  name: "Graph",
  props:['options','series'],

};
</script>

<style scoped>
#graph {
  width: 100vw;
  height: 100vh;

  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
