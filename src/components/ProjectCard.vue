<script>
export default {
  props: { project: Object },
  computed: {
    abstract() {
      const content = this.project.content;
      return content.length > 45 ? content.substr(0, 45) + "..." : content;
    },
  },
};
</script>

<template>
  <div class="col">
    <div class="card h-100">
      <img
        :src="project.image ? project.image : 'https://placehold.co/600x400'"
        class="card-img-top"
      />
      <div class="card-body">
        <span
          class="badge mb-2"
          :style="'background-color : ' + project.category.color"
          >{{ project.category.label }}</span
        >
        <h5 class="card-title">{{ project.title }}</h5>
        <p class="card-text">{{ abstract }}</p>
        <!-- <a href="#" class="btn btn-primary">Bottone</a> -->
      </div>
    </div>
    <div class="card-footer">
      <span
        :style="'background-color : ' + tecnology.color"
        class="badge me-2"
        v-for="tecnology in project.tecnologies"
        >{{ project.label }}</span
      >
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
