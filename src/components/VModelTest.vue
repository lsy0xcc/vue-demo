<template>
  <input type="text" :value="title" @input="update" />
</template>

<script>
export default {
  props: {
    title: String,
  },
  methods: {
    update(e) {
      this.$emit("update:title", e.target.value);
    },
  },
  emits: ["update:title"],
};
</script>

<style></style>
