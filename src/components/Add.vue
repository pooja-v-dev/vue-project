<template>
    <button @click="add">Add</button>
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
    add() {
      this.result = parseInt(this.inp1) + parseInt(this.inp2);
      this.$emit('add',this.result);
    },
  },
};
</script>
