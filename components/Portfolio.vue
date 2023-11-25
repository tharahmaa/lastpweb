<template>
    <section class="page-section bg-gray-100" id="portfolio">
      <div class="container mx-auto">
        <div class="text-center">
          <h2 class="section-heading text-3xl font-extrabold">Recipe</h2>
          <h3 class="section-subheading text-gray-600">Bikinnya gampang kok!</h3>
        </div>
  
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="(recipe, index) in recipes" :key="index" class="mb-8">
            <div class="relative">
              <button @click="openModal(index)" class="absolute inset-0 w-full h-full bg-transparent">
                <div class="absolute inset-0 flex items-center justify-center">
                  <i class="fas fa-plus fa-3x text-white"></i>
                </div>
              </button>
              <img class="w-full h-full object-cover" :src="recipe.image" :alt="recipe.name" />
            </div>
            <div class="text-center mt-4">
              <div class="font-bold text-lg">{{ recipe.name }}</div>
              <div class="text-gray-600">{{ recipe.description }}</div>
            </div>
          </div>
        </div>
  
        <!-- Modals -->
        <div v-for="(recipe, index) in recipes" :key="index">
          <b-modal v-if="activeModal === index" title="Modal title" @hidden="closeModal(index)">
            <p>{{ recipe.details }}</p>
            <button class="btn btn-secondary" @click="closeModal(index)">Close</button>
          </b-modal>
        </div>
      </div>
    </section>
  </template>
  
<script>
  export default {
    data() {
      return {
        activeModal: null,
        hoveredIndex: null,
        recipes: [
          {
            name: 'Brownies',
            image: '/bronis.jpg',
            description: 'Dijamin crispy di luar dan lembut di dalam.',
            details: `
            Fudgy brownies<br>
            Bahan:
            40 gr butter <br>
            40 gr margarin <br>
            225 gr coklat dcc <br>
            200 gr gula halus <br>
            80 gr tepung <br>
            30 gr coklat bubuk <br>
            2 gr kopi bubuk <br>
            3 telur <br>
            1 sdt pasta vanilla <br>
            1/4 sdt soda kue <br>
            1 gr garam <br>
            Cara membuat:
            1. Lelehkan butter, margarin, dan coklat dcc.
            2. Kocok telur & gula sampai larut.
            3. Tambahkan lelehan butter, margarin, dan coklat dcc.
            4. Aduk rata. 
            5. Masukkan tepung, kopi, coklat bubuk, soda kue, vanilla, dan garam.
            6. Panaskan oven di suhu 180 derajat celcius selama 20 menit.
            7. Tuang adonan ke loyang.
            8. Panggang adonan selama 30 menit.
            9. Jika sudah matang, tunggu brownies sampai dingin, baru dipotong kecil-kecil.
            Brownies siap disajikan.
            `,
          },
          {
            name: 'Ice Cream',
            image: '/eskrim.jpg',
            description: 'Rasakan kenikmatan lumernya eskrim di mulut.',
            details: `
            Ice Cream
            Bahan:
            1,5 cups susu
            0,5 cup coklat bubuk
            1 cup gula
            2 cups heavy cream
            1 sendok teh vanilla extract
            Cara membuat:
            1. Kocok susu, coklat bubuk, dan gula hingga larut dan rata.
            2. Di wadah terpisah, kocok heavy cream hinggal mengental.
            3. Campur rata heavy cream dan campuran susu, tambahkan vanilla extract.
            4. Masukkan ke lemari pendingin (bukan freezer), setidaknya 30 menit.
            5. Aduk lagi adonan eskrim agar nanti hasilnya lembut.
            6. Masukkan ke freezer setidaknya 2 jam.
            Es krim siap disajikan.
            `,
          },
          {
            name: 'Mochi',
            image: '/mochi.jpg',
            description: 'Pasti kenyal lembut di mulut!',
            details: `
            Chocolate Mochi
            Bahan:
            300 gr tepung ketan
            10 gr coklat bubuk
            50 gr minyak
            250 gr air
            2 gr vanili bubuk / ekstrak vanila
            2 gr garam
            140 gr kental manis putih
            500 gr eskrim coklat
            100 gr tepung tapioka sangrai
            Cara membuat:
            1. Siapkan mangkok, masukkan tepung ketan, kental manis, garam, coklat bubuk, minyak, vanila bubuk, dan air, aduk hingga rata.
            2. Pindahkan adonan mochi ke dalam wadah tahan panas, tutup dengan aluminium foil, kukus selama 35-40 menit.
            3. Uleni adonan yang sudah matang sampai kalis dan tidak lengket.
            4. Taburkan tepung tapioka yang sudah disangrai agar mochi tidak lengket.
            5. Pipihkan adonan, ambil 1 scoop eskrim, tutup adonan sampai rapat agar tidak ada eskrim yang bocor.
            6. Balurkan mochi yang sudah jadi dengan tepung tapioka lagi.
            7. Masukkan segera ke dalam freezer agar eskrim tidak meleleh.
            Mochi siap disajikan.
            `,
          },
        ],
      };
    },
    methods: {
      openModal(index) {
        this.activeModal = index;
      },
      closeModal(index) {
        this.activeModal = null;
      },
      handleHover(index) {
        this.hoveredIndex = index;
      },
    },
  };
  </script>
  
<style scoped>
  .recipe-item .fa-plus {
    opacity: 0;
    transition: opacity 0.3s ease-in-out;
  }

  .recipe-item:hover .fa-plus {
    opacity: 1;
  }

  .animated {
    animation-duration: 1s;
  }

  .fadeIn {
    animation-name: fadeIn;
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
</style>
  