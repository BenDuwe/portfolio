<template>
  <div class="portfolio">
    <h2>Projects</h2>

    <Project
      title="CSS flexbox - Minesweeper"
      discription="A minesweeper-field created using HTML5 and CSS3. The goal was the learn flexbox."
      repository="https://github.com/BenDuwe/learning-html-and-CSS/tree/master/02.flexbox-minefield"
      page="https://benduwe.github.io/learning-html-and-CSS/02.flexbox-minefield/"
      image="minefield.png"
    />
    <Project
      title="CSS Grid - Chessboard"
      discription="Using the power of CSS grid we were challenged to create a chessboard. As an additional challenge I also added some hover effects and some basic JavaScript interactivity on the chesspieces."
      repository="https://github.com/BenDuwe/learning-html-and-CSS/tree/master/04.grid-chessboard"
      page="https://benduwe.github.io/learning-html-and-CSS/04.grid-chessboard/"
      image="chessboard.png"
    />
    <Project
      title="Basic JavaScript RPG"
      discription="A small game where 2 players can battle each other. The players can use buttons to define which move they will make next. Currently the game can only end when a player reaches 0 health. A yield functionality still needs to be implemented."
      repository="https://github.com/BenDuwe/js-RPG"
      page="https://benduwe.github.io/js-RPG/"
      image="RPG.png"
    />
    <Project
      title="Pokédex"
      discription="A pokédex created using HTML5, CSS3 and a bit of JavaScript. The right panel has some interactive elements so you can look through all 807 pokémon. THe arrows let you scroll, the searchbar lets you search for pokemon by name (needs to be exact) or number and the list-button shows a list of all the pokemon, which can then be clicked."
      repository="https://github.com/BenDuwe/learning-JavaScript/tree/master/4.js-DOM-manipulation"
      page="https://benduwe.github.io/learning-JavaScript/4.js-DOM-manipulation/"
      image="pokedex.png"
    />
    <Project
      title="Basic JavaScript RPG"
      discription="A small game where 2 players can battle each other. The players can use buttons to define which move they will make next. Currently the game can only end when a player reaches 0 health. A yield functionality still needs to be implemented."
      repository="https://github.com/BenDuwe/js-RPG"
      page="https://benduwe.github.io/js-RPG/"
      image="RPG.png"
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
  }
};
</script>

<style scoped>
/* .portfolio {
  padding: 15px;
} */
</style>