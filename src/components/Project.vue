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
        <div class="aspects">
          <div class="skills">{{skills}}</div>
        </div>
        <p>{{description}}</p>
        <div class="buttons">
          <button>
            <a
              title="View code"
              :href="repository"
              rel="noopener noreferrer"
              target="_blank"
            >View code</a>
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
    skills: String,
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
  padding: 1em 1em 1em 1em;
  margin: -1rem;
  /* margin-top: -1rem; */
  /* clip-path: polygon(0 7%, 100% 0, 100% 100%, 0 93%);
  -webkit-clip-path: polygon(0 7%, 100% 0, 100% 100%, 0 93%); */
}

.bg {
  margin: 0 -1rem;
  background: rgb(244, 246, 247);
  clip-path: polygon(0% 0%, 100% 7%, 100% 93%, 0 100%);
  -webkit-clip-path: polygon(0% 0%, 100% 7%, 100% 93%, 0 100%);
}

.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 1rem 0;
}
.aspects {
  display: flex;
  width: fit-content;
  font-style: italic;
  opacity: 0.5;
  transition: all 0.3s ease-in-out;
}
.aspects:hover {
  opacity: 1;
}
h4 {
  margin-right: 0.3rem;
}
.skills {
  text-transform: uppercase;
  font-weight: 400;
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
  transform: scale(1);
  transition: all 0.5s ease-in-out;
}
.screenshot img:hover {
  transform: scale(1.1);
}
</style>