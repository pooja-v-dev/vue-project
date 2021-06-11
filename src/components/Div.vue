<template>
    <button @click="div">Div</button>
</template>
<script>
export default {
  props: ["inp1", "inp2"],
  data() {  
    return {
      result: null,
    };
  },
  methods: {
    div() {
      this.result = parseInt(this.inp1) / parseInt(this.inp2);
      this.$emit('div',this.result);
    },
  },
};
</script>
