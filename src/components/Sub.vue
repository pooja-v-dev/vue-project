<template>
    <button @click="sub">Sub</button>
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
    sub() {
      this.result = parseInt(this.inp1) - parseInt(this.inp2);
      this.$emit('sub',this.result);
    },
  },
};
</script>
