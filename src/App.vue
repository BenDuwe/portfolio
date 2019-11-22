<template>
  <div id="app">
    <Navbar />
    <Splash />
    <div class="content">
      <About />
      <Portfolio />
      <Contact />
      <div class="scroll-up">
        <a class="go-up" href="#top">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
            <path
              d="M0 16.67l2.829 2.83 9.175-9.339 9.167 9.339 2.829-2.83-11.996-12.17z"
              fill="#FCFCFC"
            />
          </svg>
        </a>
      </div>
    </div>
    <!-- <transition name="fade" mode="out-in">
      <router-view />
    </transition>-->
    <Footer />
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import Splash from "./components/Splash";
import About from "./views/About";
import Portfolio from "./views/Portfolio";
import Contact from "./views/Contact";
import Footer from "./components/Footer";
export default {
  name: "App",
  components: {
    Navbar,
    Splash,
    About,
    Portfolio,
    Contact,
    Footer
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
html {
  overflow-x: hidden;
  scroll-behavior: smooth;
  z-index: -10;
}
body {
  background: #fcfcfc;
  z-index: -9;
}

button {
  position: relative;
  padding: 5px 0;
  width: 6rem;
  border: none;
  cursor: pointer;
  background-color: transparent;
  border-radius: 0;
  transition: border-radius 0.1s ease-in-out;
}

button::after {
  position: absolute;
  content: "";
  height: 100%;
  width: calc(100% + 4px);
  top: 0;
  left: -2px;
  background: linear-gradient(
    to right,
    #ff312e 3%,
    transparent 3%,
    transparent 97%,
    #ff312e 97%
  );
  z-index: -1;
  transition: all 0.3s ease-in-out;
}
button:hover::after {
  height: 20%;
  top: 50%;
  transform: translateY(-50%);
}
button a {
  overflow: hidden;
  white-space: nowrap;

  text-decoration: none;
  font-weight: 700;
  height: 100%;
  background-image: linear-gradient(
    to right,
    #2c3e50,
    #2c3e50 50%,
    #ff312e 50%,
    #ff312e
  );
  background-size: 200% 100%;

  /* background-image: linear-gradient(
    to right,
    #ff312e 0%,
    #2c3e50 100%
  ); */

  background-clip: text;
  -webkit-background-clip: text;
  color: transparent; /*#2c3e50*/
  position: relative;
  transition: all 0.3s ease-in-out;
  -webkit-transition: all 0.3s ease-in-out;
}
/* button a::before {
  overflow: hidden;
  white-space: nowrap;
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 0%;
  content: attr(title);
  color: transparent;
  background-clip: text;
  -webkit-background-clip: text;

  background-color: #ff312e;
  transition: all 0.3s ease-in-out;
} */
/* button a::after {
  overflow: hidden;
  white-space: nowrap;
  position: absolute;
  bottom: 0;
  right: 0;
  height: 100%;
  width: 100%;
  content: attr(title);
  color: transparent;
  background-clip: text;
  -webkit-background-clip: text;

  background-color: #2c3e50;
  transition: all 0.3s ease-in-out;
} */

button:hover > a {
  background-position: -100% 0;
  /* background-image: linear-gradient(
    to right,
    #ff312e 100%,
    #2c3e50 0%
  ); */
  /* color: transparent; */
}
/* button:hover > a::before {
  width: 100%;
} */
/* button:hover > a::after {
  width: 0%;
} */

button:hover {
  /* border: 2px outset #8b2635; */
  border-radius: 0 0.5rem 0;
}

/*Getting the anchors adjusted */
.anchor > a:first-child {
  position: absolute;
  left: 0px;
  top: -4rem;
}
.anchor {
  position: relative;
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

.content {
  position: relative;
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

.scroll-up {
  opacity: 0.3;
  height: 2rem;
  width: 2rem;
  background-color: #2c383b;
  position: sticky;
  bottom: 0.5rem;
  right: 0.5rem;
  margin: 1rem 0 0 auto;
  transition: opacity 0.5s;
}
.scroll-up:hover {
  opacity: 1;
}
.go-up {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 2rem;
  width: 2rem;
}

@media screen and (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }
}
</style>
