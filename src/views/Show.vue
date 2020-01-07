<template>
  <div class="show">
    <section class="wrapper style1 align-center">
      <div class="inner">
        <h2>{{ user.first_name }}</h2>
        <div class="items style1 medium onscroll-fade-in">
          <section>
            <span class="icon solid style2 major fa-desktop"></span>

            <h3>Experience</h3>
            <p>
              {{ experiences[0].company_name }}
            </p>

            <blockquote class="twitter-tweet" data-lang="en">
              <p lang="en" dir="ltr">
                I&#39;ve been using Mailbrew to keep up with Twitter peeps who don&#39;t post often, but whom I&#39;d
                really hate to miss what they have to say. It&#39;s pretty awesome. In many ways, Twitter-over-email is
                the healthier twitter!
                <a href="https://t.co/aOgictoZir">https://t.co/aOgictoZir</a>
              </p>
              &mdash; DHH (@dhh)
              <a href="https://twitter.com/dhh/status/1214356945932435457?ref_src=twsrc%5Etfw">January 7, 2020</a>
            </blockquote>
          </section>
          <section>
            <span class="icon solid style2 major fa-bolt"></span>
            <h3>Capstone</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>

            <blockquote class="twitter-tweet" data-lang="en">
              <p lang="en" dir="ltr">
                &quot;Can you believe we used to willingly tell Google about every single visitor to
                <a href="https://t.co/fRSG4AOPoq">https://t.co/fRSG4AOPoq</a>
                by way of Google Analytics? Letting them collect every last byte of information possible through the
                spying eye of their tracking pixel. Ugh.&quot;
                <a href="https://t.co/HLEk0yffDH">https://t.co/HLEk0yffDH</a>
              </p>
              &mdash; DHH (@dhh)
              <a href="https://twitter.com/dhh/status/1214337991969128448?ref_src=twsrc%5Etfw">January 7, 2020</a>
            </blockquote>
          </section>
          <section>
            <span class="icon solid style2 major fa-envelope"></span>
            <h3>Education</h3>
            <p>
              {{ educations[0].university_name }}
            </p>

            <blockquote class="twitter-tweet" data-lang="en">
              <p lang="en" dir="ltr">
                Unaccountable algorithms with real-life consequences are not just confined to finance. How about getting
                denied staying at an Airbnb because THE ALGORITHM said no? Or forced to pay a higher price?
                <a href="https://t.co/KQ88KtoUub">https://t.co/KQ88KtoUub</a>
              </p>
              &mdash; DHH (@dhh)
              <a href="https://twitter.com/dhh/status/1214305006968401921?ref_src=twsrc%5Etfw">January 6, 2020</a>
            </blockquote>
          </section>
          <section>
            <span class="icon solid style2 major fa-cog"></span>
            <h3>Skills</h3>
            <p>
              {{ skills[0].skill_name }}
            </p>

            <blockquote class="twitter-tweet" data-lang="en">
              <p lang="en" dir="ltr">
                Starting out 2020 strong: We just removed the final third-party tracker from
                <a href="https://t.co/fRSG4AOPoq">https://t.co/fRSG4AOPoq</a>
                . All analysis is now done in-house. Thanks
                <a href="https://twitter.com/AdamStddrd?ref_src=twsrc%5Etfw">@adamstddrd</a>
                ❤️👏
                <a href="https://t.co/EDxKhKlVkb">pic.twitter.com/EDxKhKlVkb</a>
              </p>
              &mdash; DHH (@dhh)
              <a href="https://twitter.com/dhh/status/1214298483387011072?ref_src=twsrc%5Etfw">January 6, 2020</a>
            </blockquote>
          </section>
          <section>
            <span class="icon solid style2 major fa-phone"></span>
            <h3>Contact Info</h3>
            <p>
              {{ user.email }}
            </p>

            <blockquote class="twitter-tweet" data-lang="en">
              <p lang="en" dir="ltr">
                Oh, I don&#39;t need to know
                <br />
                Everything about you
                <br />
                Oh, I don&#39;t want to know
                <br />
                And you don&#39;t need to know
                <br />
                That much about me
                <br />
                <br />
                - Wilco, singing about privacy in 2009
              </p>
              &mdash; DHH (@dhh)
              <a href="https://twitter.com/dhh/status/1214327334406217728?ref_src=twsrc%5Etfw">January 6, 2020</a>
            </blockquote>
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
      user: {},
      educations: [],
      capstones: [],
      skills: [],
      experiences: []
    };
  },
  created: function() {
    axios.get("/api/users/" + this.$route.params.id).then(response => {
      this.user = response.data;
    });
    axios.get("/api/educations").then(response => {
      this.educations = response.data;
    });
    axios.get("/api/capstones").then(response => {
      this.capstones = response.data;
    });
    axios.get("/api/skills").then(response => {
      this.skills = response.data;
    });
    axios.get("/api/experiences").then(response => {
      this.experiences = response.data;
    });
  },
  methods: {}
};
</script>
