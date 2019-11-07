<template>
  <div class="portfolio">
    <h2>Projects</h2>

    <Project
      msg="Welcome to my projects page, I'm just checking if my router works. And wheter or not I am able to pass a message through."
    />
  </div>
</template>

<script>
// @ is an alias to /src
import Project from "@/components/Project.vue";

export default {
  name: "portfolio",
  components: {
    Project
  }
};
</script>

<style scoped>
/* .portfolio {
  padding: 15px;
} */
</style>