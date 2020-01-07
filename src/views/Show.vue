<template>
  <div class="show">
    <blockquote class="twitter-tweet" data-lang="en">
      <p lang="en" dir="ltr">
        I&#39;ve been using Mailbrew to keep up with Twitter peeps who don&#39;t post often, but whom I&#39;d really
        hate to miss what they have to say. It&#39;s pretty awesome. In many ways, Twitter-over-email is the healthier
        twitter!
        <a href="https://t.co/aOgictoZir">https://t.co/aOgictoZir</a>
      </p>
      &mdash; DHH (@dhh)
      <a href="https://twitter.com/dhh/status/1214356945932435457?ref_src=twsrc%5Etfw">January 7, 2020</a>
    </blockquote>

    <section class="wrapper style1 align-center">
      <div class="inner">
        <h2>{{ user.first_name }}</h2>
        <div class="items style1 medium onscroll-fade-in">
          <section>
            <span class="icon solid style2 major fa-desktop"></span>

            <h3>Experience</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-bolt"></span>
            <h3>Capstone</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-envelope"></span>
            <h3>Education</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-cog"></span>
            <h3>Skills</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-phone"></span>
            <h3>Contact Info</h3>
            <p>
              {{ user.email }}
            </p>
          </section>
        </div>
      </div>
    </section>
  </div>
</template>

<style>
.show {
  background-image: url("");
  background-repeat: no-repeat;
  opacity: 0.9;
  background-size: 100%;
}
</style>

<script>
import { Tweet, Moment, Timeline } from "vue-tweet-embed";
import axios from "axios";
export default {
  data: function() {
    return {
      user: {}
    };
  },
  created: function() {
    axios.get("/api/users/" + this.$route.params.id).then(response => {
      this.user = response.data;
    });
  },
  methods: {}
};
</script>
