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
  text-decoration: none;
}

#app {
  min-height: 100vh;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  position: relative;
}
.one-screen {
  height: 100vh;
}
.home-padding {
  padding: 1em 1em 3.3em 1em;
}
h2 {
  padding-bottom: 1em;
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
footer {
  margin: 0 -1em;
}
</style>
