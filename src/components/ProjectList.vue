<script>
import { api, store } from "../store";
import axios from "axios";

import ProjectCard from "./ProjectCard.vue";

export default {
  data() {
    return {
      store,
    };
  },

  methods: {
    fetchProjects(endpoint = api.baseUrl + "projects") {
      axios.get(endpoint).then((response) => {
        store.projects = response.data.data;
      });
    },
  },

  components: { ProjectCard },

  created() {
    this.fetchProjects();
  },
};
</script>

<template>
  <div class="row row-cols-4 g-3">
    <project-card v-for="project in store.projects" :project="project" />
  </div>
</template>

<style lang="scss" scoped></style>
