<template>
  <div>
    <div class="banner">
      <h1 class="h1">UNIVERSITY DATA RETRIEVAL SYSTEM</h1>
      <h3 class="h3">Welcome to my Final Project</h3>

      <div class="aclass">
        <a href="https://mycharger.newhaven.edu/" target="_blank"
          >University of New Haven - Website Link</a
        >
      </div>
    </div>

    <div class="container">
      <Header heading="Student Details" description="FALL 2023" />

      <button @click="toggle = !toggle">
        Toggle between Students and Faculties</button
      >`

      <div v-if="toggle">
        <StudentInfo :students="students" />
      </div>
      <div v-else>
        <FacultyInfo :faculties="faculties" />
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/HeaderComponent.vue";
import StudentInfo from "./components/StudentInfo.vue";
import FacultyInfo from "./components/FacultyInfo.vue";

export default {
  name: "App",
  components: {
    Header,
    StudentInfo,
    FacultyInfo,
  },

  data() {
    return {
      students: [],
      faculties: [],
      toggle: true,
    };
  },
  methods: {
    async fetchStudents() {
      const res = await fetch("https://webfinalprojectnode.onrender.com/api");
      const data = await res
        .json()
        .catch(() => console.log("Error in getting json data"));
      console.log(data.students);
      return data.students;
    },

    async fetchFaculties() {
      const res = await fetch(
        "https://webfinalprojectnode.onrender.com/api/faculty"
      );
      const data = await res
        .json()
        .catch(() => console.log("Error in getting json data"));
      console.log(data.faculty);
      const faculties = data.faculty;
      return faculties;
    },
  },

  async created() {
    this.students = await this.fetchStudents();
    this.faculties = await this.fetchFaculties();
    console.log("Inside created");
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.banner {
  padding: 5px;
  background-color: #f5f1f0;
  color: #4eaaba;
  font-weight: bolder;
  margin: 0;
}

.container {
  font-family: "Montserrat", sans-serif;
  overflow: auto;
  min-height: 300px;
  padding: 30px;
  background-color: #f7e6ea;
  text-align: center;
}

div {
  margin-bottom: 0.5em;
}

.h1 {
  margin-top: 2%;
  text-align: center;
  text-decoration: underline;
}

button {
  background-color: sandstone;
  text-align: center;
  text-color: black;
  color: white;
  padding: 2%;
  margin: 5px;
  margin-bottom: 12px;
  font-size: large;
  border-radius: 15px;
}

button:hover {
  filter: invert();
}

.h1:hover {
  filter: invert();
}

.h3 {
  margin-top: 2%;
  text-align: center;
  color: #d5d5db;
}

a {
  text-align: center;
  text-decoration: none;
  color: #8497b3;
  filter: invert();
}

a:hover {
  color: white;
}

.aclass {
  text-align: center;
  font-size: 2rem;
}
</style>
