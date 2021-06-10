<template>
  <div>
    <h1>This is the main file which has 4 components imported</h1>
  </div>
  <red-component> </red-component>
  <green-component></green-component>
  <yellow-component></yellow-component>
  <blue-component></blue-component>
</template>
<script>
import RedComponent from './components/RedComponent.vue';
import GreenComponent from './components/GreenComponent.vue';
import YellowComponent from './components/YellowComponent.vue';
import BlueComponent from './components/BlueComponent.vue'

export default {
  components: {
   'red-component': RedComponent,
   'green-component': GreenComponent,
   'yellow-component': YellowComponent,
   'blue-component': BlueComponent
  },
  data() {
    return {};
  },
  methods: {},
};
</script>