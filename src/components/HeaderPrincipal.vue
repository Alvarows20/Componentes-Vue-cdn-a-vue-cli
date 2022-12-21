<template>
  <div class="bg-green">
    <h1 class="py-10">{{ listHeaders.namePrincipal }}</h1>
    <h2 class="py-10">{{ listHeaders.nameAuthor }}</h2>
    <h3 class="py-5">{{ listHeaders.nameCourse }}</h3>
  </div>
</template>
<script>
export default {
  props: {
    listHeaders: Object,
  },
  data() {
    return {};
  },
};
</script>
<style scoped>
.bg-green {
  background-color: #4dd69e;
  padding: 1.2rem;
  color: #02326b;
  font-weight: 700;
  text-align: center;
}
</style>
