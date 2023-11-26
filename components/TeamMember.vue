<template>
    <div class="col-lg-4">
      <div class="team-member">
        <img :src="photo" alt="..." class="mx-auto rounded-full" />
        <h4 class="text-xl font-semibold">{{ name }}</h4>
        <p class="text-gray-600">{{ description }}</p>
        <div class="social-links">
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      name: String,
      photo: String,
      description: String,
      socialLinks: Array,
    },
  };
  </script>
  
  <style scoped>
  /* Gaya tambahan khusus untuk komponen ini jika diperlukan */
  </style>
  