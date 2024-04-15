<script>
import ProjectList from "../components/ProjectList.vue";
export default {
  data() {},
  components: { ProjectList },
};
</script>

<template>
  <h1>{{ title }}</h1>

  <project-list />
</template>

<style lang="scss">
@import "/src/scss/general.scss";
</style>
