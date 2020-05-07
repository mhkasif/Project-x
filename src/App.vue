<template>
  <div id="app">
    <ProjectHeading />
    <Input v-bind:value="value" v-on:add-val='handleSubmit' />
    <Graph v-bind:options="options" v-bind:series="series" />
  </div>
</template>

<script>
import ProjectHeading from "./components/ProjectHeading";
import Input from "./components/Input";
import Graph from "./components/Graph";
export default {
  name: "App",
  components: {
    ProjectHeading,
    Input,
    Graph,
  },
  options: {
    chart: {
      id: "vuechart-example",
    },
    xaxis: {
      categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
    },
  },
  series: [
    {
      name: "series-1",
      data: [30, 40, 45, 50, 49, 60, 70, 91],
    },
  ],
  value: "",
   handleSubmit(e){
        e.preventDefault()
        console.log(this.value)
    }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
