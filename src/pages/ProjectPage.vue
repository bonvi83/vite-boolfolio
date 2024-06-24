<script>
import axios from "axios";
import { api } from "../store";

import ProjectCard from "../components/ProjectCard.vue";

export default {
  data() {
    return {
      project: null,
    };
  },

  components: { ProjectCard },

  created() {
    console.log(this.$route.params.slug);
    const postSlug = this.$route.params.slug;
    axios.get(api.baseUrl + `/projects/${postSlug}`).then((response) => {
      this.project = response.data;
    });
  },
};
</script>

<template>
  <div class="row">
    <project-card :project="project" :isDetail="true" />
  </div>
</template>

<style lang="scss">
@import "/src/scss/general.scss";
</style>
