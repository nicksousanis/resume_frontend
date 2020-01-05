<template>
  <div class="about">
    <h2>{{ student[0].first_name }} {{ student[0].last_name }}</h2>
    <h1>Experience</h1>

    <h1>Education</h1>

    <h1>Skills</h1>

    <h1>Capstone</h1>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function() {
    return {
      student: []
    };
  },
  created: function() {
    this.student = [{ first_name: "Eddie", last_name: "O" }];
    console.log(this.user);
    axios.get("/api/students/" + this.$route.params.id).then(response => {
      this.student = response.data;
    });
  },
  methods: {}
};
</script>
