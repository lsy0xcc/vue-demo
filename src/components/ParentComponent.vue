<template>
  <div>
    <div>
      <h2>data</h2>
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
    <div>
      <h2>v-model</h2>
      <v-model-test v-model:title="title"></v-model-test>
    </div>
  </div>
</template>

<script>
import ChildComponent from "./ChildComponent.vue";
import VModelTest from "./VModelTest.vue";
export default {
  components: {
    ChildComponent,
    VModelTest,
  },
  data() {
    return {
      myData: [],
      childData: [],
      title: "",
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
