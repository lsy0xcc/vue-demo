<template>
  <div>
    <div>parentData: {{ parentData }}</div>
    <div>myData: {{ myData }}</div>
    <div><button @click="generate">click</button></div>
    <div>{{ $attrs }}</div>
  </div>
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
  mounted() {
    // console.log(this.$attrs);
  },
  methods: {
    generate() {
      let newNum = Math.random();
      this.myData.push(newNum);
      this.$emit("getNewNum", newNum);
    },
  },
  emits: {
    getNewNum(num) {
      console.log(num);
      if (num < 0.5) {
        console.log(num);
        return false;
      } else {
        return true;
      }
    },
  },
};
</script>
<style scoped></style>
