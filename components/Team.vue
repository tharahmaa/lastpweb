<template>
    <section class="page-section bg-light" id="team">
      <div class="container">
        <div class="text-center">
          <h2 class="section-heading text-uppercase">Our Amazing Team</h2>
          <h3 class="section-subheading text-muted">P17 eaakk</h3>
        </div>
        <div class="row">
          <TeamMember
            v-for="member in teamMembers"
            :key="member.id"
            :name="member.name"
            :photo="member.photo"
            :description="member.description"
            :socialLinks="member.socialLinks"
          />
        </div>
        <div class="row">
          <div class="col-lg-8 mx-auto text-center">
            <p class="large text-muted">
              LAST MODUL YEAY!!
            </p>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  import TeamMember from "@/components/TeamMember";
  
  export default {
    components: {
      TeamMember,
    },
    data() {
      return {
        teamMembers: [
          {
            id: 1,
            name: "Agas Ananta Wijaya",
            photo: "/dino1.jpg",
            description: "5027221004",
          },
          {
            id: 2,
            name: "Sylvia Febrianti",
            photo: "/dino.jpg",
            description: "5027221019",
          },
          {
            id: 3,
            name: "Atha Rahma Arianti",
            photo: "/dino2.jpg",
            description: "5027221030",
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  /* Add any additional styles here */
  </style>
  