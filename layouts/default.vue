<template>
  <v-app>
    <Navbar />
    <Nuxt />
    <CallToAction />
    <Footer />
  </v-app>
</template>

<script>
import Navbar from '../components/Navbar.vue';
import Footer from '../components/Footer.vue';
import CallToAction from '../components/CallToAction.vue';


export default {
  // name: 'DefaultLayout',
  data() {
    return {}
  },
  components: {
    Navbar,
    Footer,
    CallToAction,
  }
}
</script>