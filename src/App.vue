<script>
import axios from "axios";

export default {
  data() {
    return {
      title: "Boolpress Frontend",
      projects: [],
    };
  },

  created() {
    axios.get("http://127.0.0.1:8000/api/projects").then((response) => {});
    // console.log(response.data.data);
    this.projects = response.data.data;
  },
};
</script>

<template>
  <div class="container mt-5">
    <h1>{{ title }}</h1>
    <div v-for="project in projects">
      <ul>
        <li>
          <strong>Title:</strong>
          {{ project.title }}
        </li>
        <li>
          <strong>Content:</strong>
          {{ project.content }}
        </li>
      </ul>
      <hr />
    </div>
  </div>
</template>

<style lang="scss">
@use "/src/scss/general.scss" as *;
</style>
