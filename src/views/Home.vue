<template>
  <div class="home">
    <Splash />
  </div>
</template>

<script>
// @ is an alias to /src
import Splash from "@/components/Splash.vue";

export default {
  name: "home",
  components: {
    Splash
  }
};
</script>

<style scoped>
.home {
  flex-grow: 1;
  display: flex;
}
</style>
