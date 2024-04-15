<script>
export default {
  data() {
    return {
      title: "Home Page di Boolfolio",
    };
  },
};
</script>

<template>
  <h1>Il mio Progetto {{ $router.params.slug }}</h1>
</template>

<style lang="scss">
@import "/src/scss/general.scss";
</style>
