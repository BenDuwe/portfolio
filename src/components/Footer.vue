<template>
  <footer>
    <p>
      Ben Duwé
      <span class="highlight">©2019</span>
    </p>
  </footer>
</template>

<script>
export default {
  name: "Footer"
};
</script>

<style scoped>
footer {
  position: absolute;
  bottom: 0px;
  width: 100vw;
  margin-bottom: -4em;
  padding: 1rem 0;
  color: #fcfcfc;
  background: #2c383b;
  border-top: 3px solid #4bc0b0;
  z-index: 20;
  -webkit-box-shadow: 0px 0px 10px 0px #2c383b;
  -moz-box-shadow: 0px 0px 10px 0px #2c383b;
  box-shadow: 0px 0px 10px 0px #2c383b;
}

.highlight {
  color: #ff312e;
}
</style>