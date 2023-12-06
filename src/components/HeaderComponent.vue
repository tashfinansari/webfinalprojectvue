<template>
  <div>
    <h1>{{ heading }}</h1>
    <h4>{{ description }}</h4>
  </div>
</template>

<script>
export default {
  name: "HeaderComponent",
  props: {
    heading: String,
    description: String,
  },
};
</script>

<style scoped>
div {
  text-align: center;
}

h1 {
  background-color: #f5fe96;
  padding: 3%;
  color: black;
  border-radius: 15px;
  margin: 2px;
}

h4 {
  background-color: #cbfc17;
  padding: 1%;
  color: white;
  border-radius: 15px;
}

h1:hover {
  filter: invert();
}

h4:hover {
  filter: invert();
}
</style>
