<template>
  <div id="app" v-bind:class="{ 'one-screen': $route.path === '/' }">
    <Navbar />
    <transition name="fade" mode="out-in">
      <router-view v-bind:class="{ 'home-padding': $route.path !== '/' }" />
    </transition>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
export default {
  name: "App",
  components: {
    Navbar
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
}
.one-screen {
  height: 100vh;
}
.home-padding {
  padding: 15px;
}
h2 {
  padding-bottom: 15px;
}

.fade-enter-active,
.fade-leave-active {
  transition-duration: 0.3s;
  transition-property: opacity;
  transition-timing-function: ease;
}

.fade-enter,
.fade-leave-active {
  opacity: 0;
}
</style>
