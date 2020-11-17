<template>
  <div class="hello">
    <h1>{{ labyrinth_size }}</h1>

    <table>
      <tr v-for="row in labyrinth_size" :key="row">
        <td v-for="column in labyrinth_size" :key="column"></td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "Labyrinth",
  props: {
    labyrinth_data: Array,
  },
  computed: {
    labyrinth_size: function() {
      console.log(this.labyrinth_data.length);
      return Math.sqrt(this.labyrinth_data.length);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 
 table {
   border-collapse: collapse;
   width: 100vw;
   max-width: 500px;
   height: 100vh;
   max-height: 500px;
   background-color: black;
 }

 td {
   border: 1px solid red;
 }
</style>
