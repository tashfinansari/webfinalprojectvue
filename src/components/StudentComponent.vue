<template>
  <div class="format">
    <div :class="student.published ? 'green' : 'red'">
      <h1>Student Name: {{ student.fullName }}</h1>
      <h2>Student ID: {{ student.id }}</h2>
      <h2>Marks secured: {{ student.grade }}</h2>
      <h4>Enrollment Year: {{ student.gradYear }}</h4>
      <h4>Published: {{ student.published }}</h4>
    </div>
    <div class="image" :class="student.published ? 'green' : 'red'">
      <img :src="student.image" />
    </div>

    <!-- </div> -->
  </div>
</template>

<script>
export default {
  name: "StudentComponent",
  props: {
    student: Array,
  },
};
</script>

<style scoped>
.format {
  width: 100%;
  height: 100%;
  text-align: center;
}

h4 {
  margin: 2px;
}

div {
  background-color: #ffb89e;
  color: black;
  padding: 1em;
}

.green {
  background-color: green;
}
.red {
  /* background-color: orangered !important; */
  background-color: red;
}

img {
  width: 30%;
  height: auto;
}
</style>
