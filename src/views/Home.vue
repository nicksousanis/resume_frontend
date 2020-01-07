<template>
  <div class="container">
    <!-- One -->
    <section
      class="banner style1 orient-left content-align-left image-position-right fullscreen onload-image-fade-in onload-content-fade-right"
    >
      <div class="content">
        <h1>inLinked</h1>
        <p class="major">
          This is the best website you will ever experience. Brought to you by the intelligent minds of Eddie, Nick, and
          Shloimi.
        </p>
        <!--  <ul class="actions stacked">
            <li><a href="#first" class="button big wide smooth-scroll-middle">Get Started</a></li>
          </ul> -->
      </div>
      <div class="image">
        <img src="images/banner.jpg" alt="" />
      </div>
    </section>

    <!-- Two -->
    <section
      v-for="(user, index) in users"
      class="spotlight style1  image-position-center onscroll-image-fade-in"
      :class="{
        'orient-left': index % 2 === 1,
        'content-align-right': index % 2 === 1,
        'orient-right': index % 2 === 0,
        'content-align-left': index % 2 === 0
      }"
      id="first"
    >
      <div></div>
      <div class="content">
        <h2>{{ user.email }}</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi id ante sed ex pharetra lacinia sit amet vel
          massa. Donec facilisis laoreet nulla eu bibendum. Donec ut ex risus. Fusce lorem lectus, pharetra pretium
          massa et, hendrerit vestibulum odio lorem ipsum dolor sit amet.
        </p>
        <ul class="actions stacked">
          <li>
            <router-link v-bind:to="`/users/${user.id}`" class="button">view resume</router-link>
            <!-- <a href="`/users/${user.id}`" class="button">view resume</a> -->
          </li>
        </ul>
      </div>
      <div class="image">
        <img
          src="data:image/png;base64,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"
          alt=""
        />
      </div>
    </section>

    <!-- Three -->
    <!--     <section class="spotlight style1 orient-left content-align-left image-position-center onscroll-image-fade-in">
      <div class="content">
        <h2>Tempus adipiscing</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi id ante sed ex pharetra lacinia sit amet vel
          massa. Donec facilisis laoreet nulla eu bibendum. Donec ut ex risus. Fusce lorem lectus, pharetra pretium
          massa et, hendrerit vestibulum odio lorem ipsum dolor sit amet.
        </p>
        <ul class="actions stacked">
          <li><a href="#" class="button">Learn More</a></li>
        </ul>
      </div>
      <div class="image">
        <img src="images/spotlight02.jpg" alt="" />
      </div>
    </section> -->

    <!-- Four -->
    <!--     <section class="spotlight style1 orient-right content-align-left image-position-center onscroll-image-fade-in">
      <div class="content">
        <h2>Pharetra etiam nulla</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi id ante sed ex pharetra lacinia sit amet vel
          massa. Donec facilisis laoreet nulla eu bibendum. Donec ut ex risus. Fusce lorem lectus, pharetra pretium
          massa et, hendrerit vestibulum odio lorem ipsum dolor sit amet.
        </p>
        <ul class="actions stacked">
          <li><a href="#" class="button">Learn More</a></li>
        </ul>
      </div>
      <div class="image">
        <img src="images/spotlight03.jpg" alt="" />
      </div>
    </section> -->
  </div>
</template>

<style>
.image {
  border-radius: 75%;
}
</style>

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
    axios.get("/api/users").then(response => {
      this.users = response.data;
    });
    // this.users = [
    //   {
    //     id: 1,
    //     first_name: "first name",
    //     last_name: "last name",
    //     experience: "experience",
    //     photo: "photo",
    //     job_title: "job title",
    //     company: "company"
    //   },
    //   {
    //     id: 2,
    //     first_name: "first name2",
    //     last_name: "last name",
    //     experience: "experience",
    //     photo: "photo",
    //     job_title: "job title",
    //     company: "company"
    //   }
    // ];
    console.log(this.users);
    // axios.get("/api/users").then(response => (this.users = response.data));
  },
  methods: {}
};
</script>
