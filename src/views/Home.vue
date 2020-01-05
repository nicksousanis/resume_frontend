<template>
  <div class="home">
    <h2>{{ message }}</h2>
    <h1>Experience</h1>
    <div v-for="user in users">
      {{ user.first_name }}
      {{ user.last_name }}
    </div>
    <h1>Education</h1>
    <div v-for="user in users">
      {{ user.first_name }}
      {{ user.last_name }}
    </div>
    <h1>Skills</h1>
    <div v-for="user in users">
      {{ user.first_name }}
      {{ user.last_name }}
    </div>
    <h1>Capstone</h1>
    <div v-for="user in users">
      {{ user.first_name }}
      {{ user.last_name }}
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
      users: []
    };
  },
  created: function() {
    this.users = [{ first_name: "Eddie" }, { last_name: "O" }, { first_name: "Eddie" }, { last_name: "O" }];
    console.log(this.users);
    // axios.get("/api/users").then(response => (this.users = response.data));
  },
  methods: {}
};
</script>
