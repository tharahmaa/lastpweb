<template>
  <div>
    <Navbar />
    <Masthead />
    <Services />
    <Portfolio />
    <Team />
    <Footer />
  </div>
</template>

<script>
import Vue from 'vue';
import Navbar from '~/components/Navbar.vue';
import Masthead from '~/components/Masthead.vue';
import Team from '~/components/Team.vue';
import Footer from '~/components/Footer.vue';
import Services from '~/components/Services.vue';
import Portfolio from '~/components/Portfolio.vue';

export default Vue.extend({
  name: 'IndexPage',
  components: {
    Navbar,
    Masthead,
    Services,
    Portfolio,
    Team,
    Footer,
},
  head(){
    return{
      title: 'Resep Desserts',
    };
  },
});
</script>

<!-- Add styles specific to the index page if needed -->
<style scoped>
/* Your styles here */
</style>
