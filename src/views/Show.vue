<template>
  <div class="show">
    <section class="wrapper style1 align-center">
      <div class="inner">
        <h2>{{ student.first_name }}</h2>
        <div class="items style1 medium onscroll-fade-in">
          <section>
            <span class="icon style2 major fa-gem"></span>
            <h3>Experience</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-save"></span>
            <h3>Capstone</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-chart-bar"></span>
            <h3>Education</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-wifi"></span>
            <h3>Skills</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
          <section>
            <span class="icon solid style2 major fa-wifi"></span>
            <h3>Contact Info</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi dui turpis, cursus eget orci amet aliquam
              congue semper. Etiam eget ultrices risus nec tempor elit.
            </p>
          </section>
        </div>
      </div>
    </section>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function() {
    return {
      student: {}
    };
  },
  created: function() {
    this.student = { id: 1, first_name: "Eddie", last_name: "O" };
    // console.log(this.user);
    // axios.get("/api/students/" + this.$route.params.id).then(response => {
    //   this.student = response.data;
    // });
  },
  methods: {}
};
</script>
