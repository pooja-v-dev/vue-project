<template>
    <button @click="mul">Mul</button>
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
    mul() {
      this.result = parseInt(this.inp1) * parseInt(this.inp2);
      this.$emit('mul',this.result);
    },
  },
};
</script>
