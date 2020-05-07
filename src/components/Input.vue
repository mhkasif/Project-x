<template>
  <div>
    <input placeholder="Add Number" v-model="value" type="number" />
    <button @click="$emit('add-val', value)">Add</button>
  </div>
</template>
<script>
export default {
  name: "Input",
  data() {
    return { value: "" };
  },
  methods: {
    handleChange() {
      console.log(this.value);
    },
  },
};
</script>
<style scoped>
input {
  border: none;
  outline: none;
  border-bottom: 1px solid #a8a8a8;
  width: 15rem;
  font-size: 1rem;
}
button {
  font-size: 1rem;
  width: 6rem;
  height: 2.5rem;
  /* padding: 1rem; */
  color: white;
  text-align: center;
  background-color: #128deb;
  border: none;
  border-radius: 2px;
  margin-left: 1rem;
  transition: all 0.3s;
  cursor: pointer;
}
button:active {
  transform: translateY(3px);
}
</style>
