<template>
  <div>
    <h1>This is the main file which has 4 components imported</h1>
  </div>
  <red-component> </red-component>
  <green-component></green-component>
  <yellow-component></yellow-component>
  <blue-component></blue-component>

<br><br>
<label for="array">Please enter array value</label>
  <input type="text" name="array" id="array" v-model="arrayData" />

  <div v-for="item in final_array" :key="item">
    <div v-if="item % 2 == 0">
      <h3>{{ item }} is an {{ even }} number</h3>
    </div>
    <div v-if="item % 2 != 0">
      <h3>{{ item }} is an {{ odd }} number</h3>
    </div>
  </div>
</template>
<script>
import RedComponent from "./components/RedComponent.vue";
import GreenComponent from "./components/GreenComponent.vue";
import YellowComponent from "./components/YellowComponent.vue";
import BlueComponent from "./components/BlueComponent.vue";

export default {
  components: {
    "red-component": RedComponent,
    "green-component": GreenComponent,
    "yellow-component": YellowComponent,
    "blue-component": BlueComponent,
  },
  data() {
    return {
      arrayData: "",
      even: "EVEN",
      odd: "ODD",
    };
  },
  computed: {
    final_array() {
      if (this.arrayData.length) {
        return this.arrayData.split(",");
      } else {
        return null;
      }
    },
  },
};
</script>