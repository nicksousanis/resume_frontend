<template>
  <div class="show">
    <section class="wrapper style1 align-center">
      <div class="inner">
        <div class="items style1 medium onscroll-fade-in">
          <section>
            <span class="icon style2 major fa-gem"></span>
            <h3>Lorem</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-save"></span>
            <h3>Ipsum</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-chart-bar"></span>
            <h3>Dolor</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-wifi"></span>
            <h3>Amet</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-cog"></span>
            <h3>Magna</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon style2 major fa-paper-plane"></span>
            <h3>Tempus</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-desktop"></span>
            <h3>Aliquam</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-sync-alt"></span>
            <h3>Elit</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-hashtag"></span>
            <h3>Morbi</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-bolt"></span>
            <h3>Turpis</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-envelope"></span>
            <h3>Ultrices</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-leaf"></span>
            <h3>Risus</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
        </div>
      </div>
    </section>
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
    this.student = [{ id: 1, first_name: "Eddie", last_name: "O" }];
    console.log(this.user);
    axios.get("/api/students/" + this.$route.params.id).then(response => {
      this.student = response.data;
    });
  },
  methods: {}
};
</script>
