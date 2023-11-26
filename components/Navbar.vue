<template>
  <nav :class="{ 'bg-gray': isNavBackgroundVisible }" class="text-white fixed top-0 w-full navbar-shrink z-50" id="mainNav">
    <div class="container mx-auto flex items-center justify-between py-2 px-4">
      <button class="lg:hidden text-white" @click="toggleNav">
        Menu
        <i class="fas fa-bars ml-1"></i>
      </button>
      <div class="hidden lg:flex flex-grow justify-end items-center" :class="{ 'flex-col': isNavOpen, 'hidden': !isNavOpen }">
        <nuxt-link class="nav-link" to="#services">Desserts</nuxt-link>
        <nuxt-link class="nav-link" to="#portfolio">Recipe</nuxt-link>
        <nuxt-link class="nav-link" to="#team">Team</nuxt-link>
      </div>

      <!-- Add the dropdown for mobile -->
      <div class="lg:hidden" v-if="isNavOpen">
        <nuxt-link class="nav-link" to="#services">Desserts</nuxt-link>
        <nuxt-link class="nav-link" to="#portfolio">Recipe</nuxt-link>
        <nuxt-link class="nav-link" to="#team">Team</nuxt-link>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isNavOpen: false,
      isNavBackgroundVisible: false,
    };
  },
  methods: {
    toggleNav() {
      this.isNavOpen = !this.isNavOpen;
    },
    navbarShrink() {
      const navbarCollapsible = this.$el.querySelector('#mainNav');
      if (!navbarCollapsible) {
        return;
      }
      const isScrolled = window.scrollY !== 0;
      this.isNavBackgroundVisible = isScrolled;
    },
  },
  mounted() {
    // Shrink the navbar when page is scrolled
    window.addEventListener('scroll', this.navbarShrink);

    // Collapse responsive navbar when toggler is visible
    const navbarToggler = this.$el.querySelector('.navbar-toggler');
    if (navbarToggler) {
      const responsiveNavItems = [].slice.call(this.$el.querySelectorAll('#navbarResponsive .nav-link'));

      responsiveNavItems.map((responsiveNavItem) => {
        responsiveNavItem.addEventListener('click', () => {
          if (window.getComputedStyle(navbarToggler).display !== 'none') {
            this.toggleNav();
          }
        });
      });
    }
  },

  beforeDestroy() {
    window.removeEventListener('scroll', this.navbarShrink);
  },
};
</script>


<style scoped>
/* Component-specific styles */
.nav-link {
  color: white;
  text-decoration: none;
  padding: 0.5rem 1rem;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: #a0aec0;
}

/* Updated background color and reduced padding */
.bg-custom {
  background-color: #4a5568; /* Change to the desired color */
}

/* Apply the updated background color when the navbar shrinks */
.navbar-shrink .bg-custom {
  background-color: #4a5568; /* Change to the same color as .bg-custom */
}

/* Reduce padding for the navbar when it shrinks */
.navbar-shrink {
  padding: 0.2rem 1rem; /* Adjust the padding as needed */
}
</style>
