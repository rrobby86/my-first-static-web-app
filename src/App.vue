<template>
  <div>Hello {{ value }}</div>
  <div>{{ message }}</div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      value: "World",
      message: "",
    };
  },
  async mounted() {
    const { text } = await (await fetch("/api/message")).json();
    this.message = text;
  },
};
</script>
