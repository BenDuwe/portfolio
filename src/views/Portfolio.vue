<template>
  <div class="portfolio anchor">
    <a name="portfolio"></a>
    <h2>Projects</h2>
    <Project
      v-for="project in projects"
      :class="{bg: isEven(project.id)}"
      :key="project.id"
      :title="project.title"
      :skills="project.skills"
      :description="project.description"
      :repository="project.repository"
      :page="project.page"
      :image="project.image"
    />
  </div>
</template>

<script>
// @ is an alias to /src
import Project from "@/components/Project.vue";

export default {
  name: "portfolio",
  components: {
    Project
  },
  data() {
    return {
      projects: [
        /* TEMPLATE */
        // {
        //   id:,
        //   title: "",
        //   skills:"",
        //   description: "",
        //   repository: "",
        //   page: "",
        //   image: ""
        // },
        /* Minefield */
        {
          id: 1,
          title: "CSS flexbox - Minesweeper",
          skills: "HTML / CSS",
          description:
            "A visual clone of a minesweeper-field created using HTML5 and CSS3. The goal here was the learn CSS flexbox.",
          repository:
            "https://github.com/BenDuwe/learning-html-and-CSS/tree/master/02.flexbox-minefield",
          page:
            "https://benduwe.github.io/learning-html-and-CSS/02.flexbox-minefield/",
          image: "minefield.png"
        },
        /* Chessboard */
        {
          id: 2,
          title: "CSS Grid - Chessboard",
          skills: "HTML / CSS",
          description:
            "Using the power of CSS grid we were challenged to create a chessboard. As an additional challenge I also added some hover effects and some basic JavaScript interactivity on the chesspieces.",
          repository:
            "https://github.com/BenDuwe/learning-html-and-CSS/tree/master/04.grid-chessboard",
          page:
            "https://benduwe.github.io/learning-html-and-CSS/04.grid-chessboard/",
          image: "chessboard.png"
        },
        /* Adminpanel */
        {
          id: 3,
          title: "Admin-panel recreation",
          skills: "HTML / (S)CSS",
          description:
            "As a group of 3 or 4 people, we recreated the HTML and (S)CSS for an admin panel (link to original on Github). I created the sidebar during this project.",
          repository:
            "https://github.com/BenDuwe/learning-html-and-CSS/tree/master/10.admin-panel",
          page:
            "https://benduwe.github.io/learning-html-and-CSS/10.admin-panel/",
          image: "admin.png"
        },
        /* Pokédex */
        {
          id: 4,
          title: "Pokédex",
          skills: "HTML / (S)CSS / JavaScript",
          description:
            "A pokédex created using HTML5, CSS3 and a bit of JavaScript. The right panel has some interactive elements so you can look through all 807 pokémon. THe arrows let you scroll, the searchbar lets you search for pokemon by name (needs to be exact) or number and the list-button shows a list of all the pokemon, which can then be clicked.",
          repository:
            "https://github.com/BenDuwe/learning-JavaScript/tree/master/4.js-DOM-manipulation",
          page:
            "https://benduwe.github.io/learning-JavaScript/4.js-DOM-manipulation/",
          image: "pokedex.png"
        },
        /* RPG */
        {
          id: 5,
          title: "Basic JavaScript RPG",
          skills: "HTML / (S)CSS / JavaScript",
          description:
            "A small game where 2 players can battle each other. The players can use buttons to define which move they will make next. Currently the game can only end when a player reaches 0 health. A yield functionality still needs to be implemented.",
          repository: "https://github.com/BenDuwe/js-RPG",
          page: "https://benduwe.github.io/js-RPG/",
          image: "rpg.png"
        }
      ]
    };
  },
  methods: {
    isEven: function(id) {
      return id % 2 !== 0;
    }
  }
};
</script>

<style scoped>
.portfolio {
  padding: 1rem;
}
</style>