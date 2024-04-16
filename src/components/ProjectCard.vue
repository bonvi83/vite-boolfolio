<script>
export default {
  props: { project: Object, isDetail: Boolean },
  computed: {
    abstract() {
      const content = this.project.content;
      return content.length > 45 && !this.isDetail
        ? content.substr(0, 45) + "..."
        : content;
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
        :class="isDetail ? 'w-50' : ''"
      />
      <div class="card-body">
        <span
          class="badge mb-2"
          :style="'background-color : ' + project.category.color"
          >{{ project.category.label }}</span
        >
        <h2 class="card-title h5">{{ project.title }}</h2>
        <p class="card-text float-start">{{ abstract }}</p>
        <router-link
          v.if="!isDetail"
          :to="{ name: 'project', params: { slug: project.slug } }"
          class="btn btn-primary"
          >Vedi altro</router-link
        >
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
