<script>
import axios from "axios";
import { api } from "../store";

export default {
  data() {
    return {
      project: null
    }
  },

  created() {
    const postSlug = this.$route.params.slug;
    axios.get(api.baseUrl + /projects/$projectSlug).then((responde) => {
      this.project = response.data;
    });
  },
};
</script>

<template>
  <h1>Il mio Progetto {{ $route.params.slug }}</h1>
</template>

<style lang="scss">
@import "/src/scss/general.scss";
</style>
