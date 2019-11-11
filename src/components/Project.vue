<template>
  <div class="project">
    <div class="info">
      <h3>{{title}}</h3>
      <p>{{discription}}</p>
      <ul>
        <li>
          <a :href="repository">View source</a>
        </li>
        <li>
          <a :href="page">View online</a>
        </li>
      </ul>
    </div>
    <div class="screenshot">
      <a :href="page">
        <img :src="resolve_img_url(image)" alt="Project screenshot" />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Project",
  props: {
    title: String,
    discription: String,
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
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 3rem;
}
.info {
  width: 60rem;
  padding-right: 1.5rem;
  text-align: justify;
}
ul {
  list-style: none;
  display: flex;
  justify-content: center;
}
li {
  margin: 1rem;
  padding: 1rem;
}
.screenshot {
  overflow: hidden;
  padding-left: 1.5rem;
  width: 25rem;
}
.screenshot img {
  max-width: 100%;
}
</style>