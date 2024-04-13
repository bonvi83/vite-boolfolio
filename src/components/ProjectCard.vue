<script>
export default {
  props: { project: Object },
};
</script>

<template>
  <div class="col">
    <div class="card h-100">
      <img v-if="project.image" :src="project.image" class="card-img-top" />
      <div class="card-body">
        <h5 class="card-title">{{ project.title }}</h5>
        <p class="card-text">{{ project.content }}</p>
        <a href="#" class="btn btn-primary">Bottone</a>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
