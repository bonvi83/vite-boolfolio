<script>
import { api, store } from "../store";
import axios from "axios";

export default {
  data() {
    return {
      store,
    };
  },

  created() {
    axios.get(api.baseUrl + "projects").then((response) => {});
    store.projects = response.data.data;
  },
};
</script>

<template>
  <div v-for="project in store.projects">
    <ul>
      <li><strong>ID:</strong>{{ project.id }}</li>
      <li><strong>Title:</strong>{{ project.title }}</li>
      <li><strong>Content:</strong>{{ project.content }}</li>
    </ul>
    <hr />
  </div>
</template>

<style lang="scss" scoped></style>
