<script>
export default {
  props: { pagination: Array },
  emit: ["change-page"],
};
</script>

<template>
  <nav aria-label="Page navigation">
    <ul class="pagination">
      <li
        v-for="link in pagination"
        @click="$emit('change-page', link.url)"
        class="page-item"
        :class="{
          active: link.active,
          disabled: !link.url,
        }"
      >
        <a class="page-link" href="#" v-html="link.label"></a>
      </li>
    </ul>
  </nav>
</template>

<style lang="scss" scoped></style>
