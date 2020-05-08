<template>
  <div id="app">
    <ProjectHeading />
    <Input v-on:add-val="handleSubmit" />
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
  data() {
    return {
      options: {
        // chart: {
        //   id: "vuechart-example",
        // },
        stroke: {
          width: 1,
          curve: "smooth",
        },
        xaxis: {
          categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
        },
      },
      series: [
        {
          type: "line",
          data: [],
        },
      ],
    };
  },
  mounted: function() {
    setInterval(() => {
      let arr=[];
      for (var i = 0; i < 8; i++) {
        arr.push(Math.floor(Math.random() * 101));
      }
      this.series =  [{ type: "line", data: arr }]
    }, 500);
  },
  methods: {
    handleSubmit(val) {
      // const num = Number(val);
      this.options = {
        ...this.options,
        stroke: { ...this.options.stroke, width: val },
      };
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  overflow: hidden;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100vw;
}
</style>
