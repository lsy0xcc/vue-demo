<template lang="">
  <div>
    <div>myData: {{ myData }}</div>
    <div>childData: {{ childData }}</div>
    <div>
      <button @click="generate">click</button>
    </div>
    <child-component
      :parent-data="myData"
      @get-new-num="update"
      :not-exist-attr="42"
    />
  </div>
</template>

<script>
import ChildComponent from "./ChildComponent.vue";
export default {
  components: {
    ChildComponent,
  },
  data() {
    return {
      myData: [],
      childData: [],
    };
  },
  methods: {
    generate() {
      this.myData.push(Math.random());
    },
    update(value) {
      this.childData.push(value);
    },
  },
};
</script>
<style scoped></style>
