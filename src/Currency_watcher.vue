<template>
  <div id="databinding" style="">
    <h1>Currency Converter using Watchers </h1>
    <span>Enter Amount:</span><br>
    <label>INR: <input type="number" v-model="inr" /></label><br />
    <label>USD: <input type="number" v-model="usd" /></label><br />
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      inr: 0,
      usd: 0
    };
  },
  watch: {
    inr(newVal, oldVal) {
      oldVal = newVal / 72.95;
      this.usd = oldVal;
    },
    usd(newVal, oldVal) {
      oldVal = newVal * 72.95;
      this.inr = oldVal;
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

input {
  margin: 2%;
}
</style>
