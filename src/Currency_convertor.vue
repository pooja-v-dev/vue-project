<template>
  <div id="databinding" style="">
    <h1>Currency Converter</h1>
    <span>Enter Amount:</span
    ><input
      type="number"
      v-model.number="amount"
      placeholder="Enter Amount"
    /><br /><br />
    <div class="select_cover">
      <span>Convert From:</span>
      <select v-model="convertfrom">
        <option v-for="a in currencyfrom" v-bind:key="a.name">
          {{ a.name }}
        </option>
      </select>
      <span>Convert To:</span>
      <select v-model="convertto">
        <option v-for="a in currencyfrom" v-bind:key="a.name">
          {{ a.name }}
        </option></select
      ><br /><br />
    </div>
    <span
      ><h2>
        {{ amount }} {{ convertfrom }} equals {{ finalamount }} {{ convertto }}
      </h2>
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
            final = parseFloat(this.amount * 0.014).toFixed(2);
          }

          if (to == "INR") {
            final = this.amount;
          }

          break;
        case "USD":
          if (to == "INR") {
            final = parseFloat(this.amount * 72.96).toFixed(2);
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

select{
  margin:15px;
  width: 300px; 
  font-size: 20px
}
input {
  margin: 2%;
}
</style>
