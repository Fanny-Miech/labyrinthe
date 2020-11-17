<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />

    <h1>Minautorus</h1>
    <h3>Labyrinthe for life</h3>
    <Labyrinth_select
      :labyrinth_data="labyrinth_data"
      @labyrinth_chosen="labyrinthChosen"
    />
    <Labyrinth :labyrinth_data="selected_labyrinth" />
  </div>
</template>

<script>
import labyrinthData from "./static/labyrinthes.json";
import Labyrinth_select from "./components/Labyrinth_select";
import Labyrinth from "./components/Labyrinth.vue";

export default {
  name: "App",
  components: {
    Labyrinth_select,
    Labyrinth,
  },

  data() {
    return {
      labyrinth_data: labyrinthData,
      selected_labyrinth: [],
    };
  },

  methods: {
    labyrinthChosen: function(labyrinth) {
      this.selected_labyrinth = labyrinth;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
