<template>
  <div class="container">
    <h2>all students</h2>
    <div class="card-body">
      <div v-for="student in students" class="card">
        <h4>{{ student.first_name }}</h4>
        <h4>{{ student.last_name }}</h4>
        <p>{{ student.experience }}</p>
        <p>{{ student.education }}</p>
        <p>{{ student.skills }}</p>
        <p>{{ student.capstone }}</p>
        <router-link v-bind:to="`/students/${student.id}`">More details</router-link>
      </div>
    </div>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function() {
    return {
      message: "Your profile",
      students: []
    };
  },
  created: function() {
    this.students = [
      {
        first_name: "first_name",
        last_name: "last_name",
        experience: "experience",
        education: "education",
        skills: "skills",
        capstone: "capstone"
      }
    ];
    console.log(this.students);
    // axios.get("/api/users").then(response => (this.users = response.data));
  },
  methods: {}
};
</script>
