<script>
import { api, store } from "../store";
import axios from "axios";

import ProjectCard from "./ProjectCard.vue";
import PaginationUI from "./ui/PaginationUI.vue";

export default {
  data() {
    return {
      store,
      pagination: [],
    };
  },

  methods: {
    fetchProjects(endpoint = api.baseUrl + "projects") {
      axios.get(endpoint).then((response) => {
        store.projects = response.data.data;
        this.pagination = response.data.links;
      });
    },
  },

  components: { ProjectCard, PaginationUI },

  created() {
    this.fetchProjects();
  },
};
</script>

<template>
  <pagination-ui @chenge-page="fetchProjects" :pagination="pagination" />

  <div class="row row-cols-4 g-3">
    <project-card v-for="project in store.projects" :project="project" />
  </div>

  <pagination-ui @chenge-page="fetchProjects" :pagination="pagination" />
</template>

<style lang="scss" scoped></style>
