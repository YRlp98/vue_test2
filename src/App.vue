<template>
  <div class="container">
    <Card v-for="card in cards" :key="card" :card="card"></Card>
  </div>
</template>

<script>
import Card from "./components/Card.vue";
import jsonFile from "./data.json";

export default {
  name: "App",
  components: {
    Card,
  },
  data() {
    return {
      cards: jsonFile,
    };
  },
};
</script>

<style lang="scss">
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-bottom: 40px;
}
</style>
