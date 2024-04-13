<script>
import AppHeader from "./components/AppHeader.vue";
import ProjectList from "./components/ProjectList.vue";

export default {
  data() {
    return {
      title: "Boolpress Frontend",
    };
  },

  components: { AppHeader, ProjectList },

  created() {
    axios.get(api.baseUrl + "projects").then((response) => {});
    // console.log(response.data.data);
    store.projects = response.data.data;
  },
};
</script>

<template>
  <app-header :title="title" />

  <div class="container mt-5 pb-5">
    <project-list />
  </div>
</template>

<style lang="scss">
@use "/src/scss/general.scss" as *;
</style>
