<template>
  <div class="hello">
    <form>
      <div class="form-group row">
        <label for="size" class="col-6">Select labyrinth size</label>
        <select
          class="form-control col-6"
          id="size"
          v-model="current_labyrinth_size"
        >
          <option
            v-for="(name, size) in labyrinth_data"
            :key="Object.keys(labyrinth_data).indexOf(size)"
            :value="name"
          >
            {{ size }}
          </option>
        </select>
      </div>
      <div class="form-group row">
        <label for="labyrinth" class="col-6">Chose labyrinth</label>
        <select
          class="form-control col-6"
          id="labyrinth"
          v-model="current_labyrinth"
        >
          <option
            v-for="(value, name) in current_labyrinth_size"
            :key="Object.keys(current_labyrinth_size).indexOf(name)"
            :value="value"
          >
            {{ name }}
          </option>
        </select>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "Labyrinth_select",
  data: function() {
    return {
      current_labyrinth_size: {},
      current_labyrinth: {},
    };
  },
  props: {
    labyrinth_data: Object,
  },
  watch: {
    current_labyrinth: function() {
      console.log(this.current_labyrinth);
      this.$emit("labyrinth_chosen", this.current_labyrinth);
    },
  },
};
</script>
