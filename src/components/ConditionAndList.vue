<template>
  <div>
    <ul>
      <li v-for="(item, index) in items" :key="item.id">
        {{ index + 1 }}. {{ item.id }} - {{ item.name }}
        <template v-if="item.status === 2"> complete </template>
        <template v-else-if="item.status === 1"> in process </template>
        <template v-else> not begin </template>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ConditionAndList",
  data() {
    return {
      items: [
        {
          name: "vue",
          id: 5,
          status: 1,
        },
        {
          name: "js",
          id: 1,
          status: 1,
        },
        {
          name: "ts",
          id: 1,
          status: 2,
        },
        {
          name: "jest",
          status: 0,
          id: 10,
        },
      ],
    };
  },
};
</script>

<style scoped></style>
