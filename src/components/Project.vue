<template>
  <div class="project">
    <div class="card">
      <div class="screenshot">
        <a v-if="image" :href="page" rel="noopener noreferrer" target="_blank">
          <img :src="resolve_img_url(image)" alt="Project screenshot" />
        </a>
      </div>
      <div class="info">
        <h3>{{title}}</h3>
        <p>{{description}}</p>
        <div class="buttons">
          <button>
            <a
              title="View source"
              :href="repository"
              rel="noopener noreferrer"
              target="_blank"
            >View source</a>
          </button>
          <button v-if="page">
            <a
              title="View online"
              :href="page"
              rel="noopener noreferrer"
              target="_blank"
            >View online</a>
          </button>
        </div>
      </div>
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
  padding: 1.5em 1em 1em 1em;
  margin: 0 -1rem;
  clip-path: polygon(0 10%, 100% 0, 100% 100%, 0 90%);
  -webkit-clip-path: polygon(0 10%, 100% 0, 100% 100%, 0 90%);
}

.bg {
  background: rgb(244, 246, 247) /*rgba(75, 192, 176, 0.1)*/;
  clip-path: polygon(0% 0%, 100% 10%, 100% 90%, 0 100%);
  -webkit-clip-path: polygon(0% 0%, 100% 10%, 100% 90%, 0 100%);
}

.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-bottom: 2rem;
}

.info {
  min-width: auto;
  max-width: auto;
}
p {
  text-align: justify;
}

.buttons {
  display: flex;
  justify-content: center;
  z-index: -1;
}

button {
  margin: 10px;
}

.screenshot {
  overflow: hidden;
  width: 20rem;
}
.screenshot img {
  max-height: 5rem;
  max-width: 8rem;
}
</style>