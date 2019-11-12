<template>
  <div class="project">
    <div class="screenshot">
      <a v-if="image" :href="page">
        <img :src="resolve_img_url(image)" alt="Project screenshot" />
      </a>
    </div>
    <div class="info">
      <h3>{{title}}</h3>
      <p>{{description}}</p>
      <ul>
        <li>
          <a :href="repository">View source</a>
        </li>
        <li v-if="page">
          <a :href="page">View online</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Project",
  props: {
    title: String,
    description: String,
    repository: String,
    page: String,
    image: String
  },
  methods: {
    resolve_img_url: function(path) {
      let images = require.context("../assets/", false, /\.png$|\.jpg$/);
      return images("./" + path);
    }
  }
};
</script>

<style scoped>
.project {
  z-index: -1;
  /* height: fit-content; */
  display: flex;
  flex-direction: column;
  align-items: center;
  /* margin-bottom: 3rem; */
  padding: 1rem 1em;
  margin: -1em -1em;
  clip-path: polygon(0 5%, 100% 0, 100% 100%, 0 95%);
  -webkit-clip-path: polygon(0 5%, 100% 0, 100% 100%, 0 95%);
}

.bg {
  background: rgb(231, 242, 245) /*rgba(75, 192, 176, 0.1)*/;
  clip-path: polygon(0% 0%, 100% 5%, 100% 95%, 0 100%);
  -webkit-clip-path: polygon(0% 0%, 100% 5%, 100% 95%, 0 100%);
}

.info {
  min-width: auto;
  max-width: auto;

  text-align: justify;
}
ul {
  list-style: none;
  display: flex;
  justify-content: center;
  z-index: -1;
}
li {
  margin: 0.625rem;
  padding: 0.31rem;
  border: 2px solid #ff312e;
}
ul a {
  color: #2c333b;
  background: none;
  font-weight: bold;

  position: relative;
  /* display: inline-block; */
}

.screenshot {
  overflow: hidden;
  width: 20rem;
}
.screenshot img {
  max-width: 40%;
}
</style>