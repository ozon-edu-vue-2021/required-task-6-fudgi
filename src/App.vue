<template>
  <div id="app">
    <p v-for="item in rows" :key="item.id">{{ item }}</p>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "App",
  components: {},
  data() {
    return {
      rows: [],
    };
  },
  async created() {
    const res = await axios.get(
      `https://jsonplaceholder.typicode.com/comments`
    );
    this.rows = res.data;
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
  padding: 24px;
  box-sizing: border-box;
}

html,
body,
#app {
  background-color: #e5e5e5;
}

* {
  box-sizing: border-box;
}
</style>
