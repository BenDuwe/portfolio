<template>
  <div class="project">
    <p>{{msg}}</p>
  </div>
</template>

<script>
export default {
  name: "Project",
  props: {
    msg: String
  }
};
</script>

<style scoped>
.project p {
  text-align: justify;
}
</style>