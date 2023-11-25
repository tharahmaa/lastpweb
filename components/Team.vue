<template>
    <section class="page-section bg-light" id="team">
      <div class="container">
        <div class="text-center">
          <h2 class="section-heading text-uppercase">Our Amazing Team</h2>
          <h3 class="section-subheading text-muted">P17 ea</h3>
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
              Iseng-iseng aja sih
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
            photo: "/dino.jpg",
            description: "5027221000",
            socialLinks: [
              { label: "Twitter", icon: "fab fa-twitter" },
              { label: "Facebook", icon: "fab fa-facebook-f" },
              { label: "LinkedIn", icon: "fab fa-linkedin-in" },
            ],
          },
          {
            id: 2,
            name: "Sylvia Febrianti",
            photo: "/dino.jpg",
            description: "5027221000",
            socialLinks: [
              { label: "Twitter", icon: "fab fa-twitter" },
              { label: "Facebook", icon: "fab fa-facebook-f" },
              { label: "LinkedIn", icon: "fab fa-linkedin-in" },
            ],
          },
          {
            id: 3,
            name: "Atha Rahma Arianti",
            photo: "/dino.jpg",
            description: "5027221000",
            socialLinks: [
              { label: "Twitter", icon: "fab fa-twitter" },
              { label: "Facebook", icon: "fab fa-facebook-f" },
              { label: "LinkedIn", icon: "fab fa-linkedin-in" },
            ],
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  /* Add any additional styles here */
  </style>
  