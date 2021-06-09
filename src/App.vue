<template>
  <div id="databinding" style="">
    <h1>Currency Converter</h1>
    <span>Enter Amount:</span
    ><input
      type="number"
      v-model.number="amount"
      placeholder="Enter Amount"
    /><br /><br />
    <span>Convert From:</span>
    <select v-model="convertfrom" style="width: 300px; font-size: 25px">
      <option v-for="a in currencyfrom" v-bind:key="a.name">
        {{ a.name }}
      </option>
    </select>
    <span>Convert To:</span>
    <select v-model="convertto" style="width: 300px; font-size: 25px">
      <option v-for="a in currencyfrom" v-bind:key="a.name">
        {{ a.name }}
      </option></select
    ><br /><br />
    <span>
      {{ amount }} {{ convertfrom }} equals {{ finalamount }}
      {{ convertto }}
    </span>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "",
      currencyfrom: [
        { name: "USD", desc: "US Dollar" },
        { name: "INR", desc: "Indian Rupee" },
      ],
      convertfrom: "INR",
      convertto: "USD",
      amount: "",
    };
  },
  computed: {
    finalamount: function () {
      var to = this.convertto;
      var from = this.convertfrom;
      var final;
      switch (from) {
        case "INR":
          if (to == "USD") {
            final = this.amount * 0.016;
          }

          if (to == "INR") {
            final = this.amount;
          }

          break;
        case "USD":
          if (to == "INR") {
            final = this.amount * 63.88;
          }

          if (to == "USD") {
            final = this.amount;
          }

          break;
      }
      return final;
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
