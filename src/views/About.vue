<template>
  <div class="about">
    <h2>{{ user[0].first_name }} {{ user[1].last_name }}</h2>
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
      user: []
    };
  },
  created: function() {
    this.user = [{ first_name: "Eddie" }, { last_name: "O" }];
    console.log(this.user);
    // axios.get("/api/users").then(response => (this.users = response.data));
  },
  methods: {}
};
</script>
