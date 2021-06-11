<template>
  <div>
    <h2>Calculator</h2>
  </div>
  <div>
    <label for="input1">Input 1</label>
    <input type="number" name="input1" id="input1" v-model="input1" placeholder="Enter number for I/p 1"/>
    <label for="input2">Input 2</label>
    <input type="number" name="input2" id="input2" v-model="input2" placeholder="Enter number for I/p 2"/>
  </div>
  <Add :inp1="input1" :inp2="input2" v-on:add="onAddData"></Add>
  <Sub :inp1="input1" :inp2="input2" v-on:sub="onSubData"></Sub>
  <Mul :inp1="input1" :inp2="input2" v-on:mul="onMulData"></Mul>
  <Div :inp1="input1" :inp2="input2" v-on:div="onDivData"></Div>

  <div>
    <h3>Result: {{ result }}</h3>
  </div>
</template>
<script>
import Add from "./components/Add.vue";
import Sub from "./components/Sub.vue";
import Mul from "./components/Mul.vue";
import Div from "./components/Div.vue";

export default {
  components: {
    Add,
    Sub,
    Mul,
    Div,
  },
  data() {
    return {
      input1: null,
      input2: null,
      result: null,
    };
  },
  methods: {
    onAddData(value) {
      this.result = value;
    },
    onSubData(value) {
      this.result = value;
    },
    onMulData(value) {
      this.result = value;
    },
    onDivData(value) {
      this.result = value;
    },
  },
};
</script>
<style >
input {
  margin: 15px;
}
button {
  padding: 10px;
  margin: 10px;
}
</style>
