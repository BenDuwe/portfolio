<template>
  <div class="project">
    <div class="card">
      <div class="screenshot">
        <a v-if="image" :href="page" rel="noopener noreferrer" target="_blank">
          <img :src="resolve_img_url(image)" alt="Project screenshot" />
        </a>
      </div>
      <div class="info">
        <div class="heading">
          <h3>{{title}}</h3>
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
  margin: -0.5rem -1rem;
  /* padding-top: -1rem; */
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
h4 {
  padding-right: 0.3rem;
}

.info {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  min-width: auto;
  max-width: auto;
}
.info .heading {
  display: flex;
  flex-direction: column;
  /* justify-content: flex-start; */
  align-items: center;
  width: 100%;
}
.info .heading .skills {
  text-transform: uppercase;
  font-size: 0.9rem;
  font-weight: 400;
  margin-left: 1rem;
  opacity: 1;
  transition: all 0.3s ease-in-out;
}

.project:hover {
  opacity: 1;
}
.info p {
  text-align: justify;
}
.info .buttons {
  align-self: center;
  display: flex;
  justify-content: center;
  /* z-index: 3; */
}

button {
  margin: 10px;
}

.screenshot {
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  height: 10rem;
  min-width: 10rem;
}
.screenshot img {
  height: auto;
  width: 8rem;

  transform: scale(1);
  transition: all 0.5s ease-in-out;
}
.screenshot img:hover {
  transform: scale(1.1);
}

@media only screen and (min-width: 768px) {
  .project {
    opacity: 0.9;
    transition: all 0.3s ease-in-out;
  }
  .project:hover {
    opacity: 1;
  }
  .info .heading {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
  }
  .project .info .heading .skills {
    opacity: 0.5;
  }
  .project:hover .info .heading .skills {
    color: #4bc0b0;
    opacity: 1;
  }

  .card {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }
  .screenshot img {
    height: auto;
    width: 8rem;
  }
  .project .screenshot {
    min-height: 100%;
    /* width: 33vw; */
    padding-right: 1rem;
  }
  .project .info {
    position: relative;
    width: 75vw;
    padding-left: 1rem;
    margin-left: 2.5rem;
    /* border-left: 3px solid #4bc0b0; */
  }
  .project .info::before {
    position: absolute;
    top: -1rem;
    left: -2.5rem;
    content: "";
    background: rgb(44, 56, 59);
    background: -moz-linear-gradient(
      180deg,
      rgba(44, 56, 59, 1) 0%,
      rgba(44, 56, 59, 1) 50%,
      rgba(75, 192, 176, 1) 50%,
      rgba(75, 192, 176, 1) 100%
    );
    background: -webkit-linear-gradient(
      180deg,
      rgba(44, 56, 59, 1) 0%,
      rgba(44, 56, 59, 1) 50%,
      rgba(75, 192, 176, 1) 50%,
      rgba(75, 192, 176, 1) 100%
    );
    background: linear-gradient(
      180deg,
      rgba(44, 56, 59, 1) 0%,
      rgba(44, 56, 59, 1) 50%,
      rgba(75, 192, 176, 1) 50%,
      rgba(75, 192, 176, 1) 100%
    );
    filter: progid:DXImageTransform.Microsoft.gradient(startColorstr="#2c383b",endColorstr="#4bc0b0",GradientType=1);
    background-size: 100% 200%;
    height: calc(100% + 2rem);
    width: 3px;
    transition: all 0.2s ease-in-out;
  }
  .project:hover .info::before {
    background-position: 0 -100%;
  }

  .bg .screenshot {
    order: 2;
    padding-right: 0;
    padding-left: 1rem;
  }
  .bg .info {
    padding-left: 0;
    padding-right: 1rem;
    margin-right: 2.5rem;
    margin-left: 0;

    /* border-right: 3px solid #4bc0b0; */
    /* border-left: none; */
  }
  .bg .info::after {
    position: absolute;
    top: -1rem;
    right: -2.5rem;
    content: "";
    background: rgb(44, 56, 59);
    background: -moz-linear-gradient(
      180deg,
      rgba(44, 56, 59, 1) 0%,
      rgba(44, 56, 59, 1) 50%,
      rgba(75, 192, 176, 1) 50%,
      rgba(75, 192, 176, 1) 100%
    );
    background: -webkit-linear-gradient(
      180deg,
      rgba(44, 56, 59, 1) 0%,
      rgba(44, 56, 59, 1) 50%,
      rgba(75, 192, 176, 1) 50%,
      rgba(75, 192, 176, 1) 100%
    );
    background: linear-gradient(
      180deg,
      rgba(44, 56, 59, 1) 0%,
      rgba(44, 56, 59, 1) 50%,
      rgba(75, 192, 176, 1) 50%,
      rgba(75, 192, 176, 1) 100%
    );
    filter: progid:DXImageTransform.Microsoft.gradient(startColorstr="#2c383b",endColorstr="#4bc0b0",GradientType=1);
    background-size: 100% 200%;
    height: calc(100% + 2rem);
    width: 3px;
    transition: all 0.2s ease-in-out;
  }
  .project:hover .info::after {
    background-position: 0 -100%;
  }
}
</style>