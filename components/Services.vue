<template>
    <section class="page-section" id="services">
      <div class="container mx-auto">
        <div class="text-center">
          <h2 class="section-heading text-3xl font-extrabold">Why Our Recipe?</h2>
          <h3 class="section-subheading text-gray-600">Anti gagal? Mainstream brooo</h3>
        </div>
  
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mt-8">
          <div v-for="(dessert, index) in desserts" :key="index" class="text-center">
            <div class="relative inline-block mb-4">
              <div class="rounded-full bg-primary p-2">
                <img :src="dessert.image" class="rounded-full w-80 h-80 object-cover" :alt="dessert.name" />
              </div>
            </div>
            <h4 class="text-xl font-semibold my-3">{{ dessert.name }}</h4>
            <p class="text-gray-600">{{ dessert.description }}</p>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        desserts: [
          {
            name: 'Bahan mudah dicari',
            description: 'Ga perlu ribet-ribet, semua ada di toko terdekat.',
            image: '/bahan.jpg',
          },
          {
            name: 'Cukup terjangkau',
            description: 'Bahan yang dipakai bisa disesuaikan dengan budget masing-masing',
            image: '/shop.jpg',
          },
          {
            name: 'Rasa premium',
            description: 'Walaupun murah, tapi rasa ga murahan!',
            image: '/chef.jpg',
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
    .rounded-full.bg-primary.p-2 {
      background-color: #8B4513; /* Kode warna coklat muda */
    }
  </style>
  