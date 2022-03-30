<template>
  <condition-and-list />
  <parent-component />
</template>

<script>
import ConditionAndList from "./components/ConditionAndList.vue";
import ParentComponent from "./components/ParentComponent.vue";
export default {
  name: "App",
  components: {
    ConditionAndList,
    ParentComponent,
  },
};
</script>

<style>
</style>
