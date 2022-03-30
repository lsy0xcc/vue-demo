<template>
  <div>parentData: {{ parentData }}</div>
  <div>myData: {{ myData }}</div>
  <div><button @click="generate">click</button></div>
</template>
<script>
export default {
  props: {
    parentData: Array,
  },
  data() {
    return {
      myData: [],
    };
  },
  methods: {
    generate() {
      let newNum = Math.random();
      this.myData.push(newNum);
      this.$emit("get-new-num", newNum);
    },
  },
};
</script>
<style scoped></style>
