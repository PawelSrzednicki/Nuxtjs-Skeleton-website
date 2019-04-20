<template>
  <v-app dark>
    <Navbar/>
    <v-content>
      <v-layout row wrap>
        <v-flex xs12 lg8>
          <nuxt/>
        </v-flex>
        <v-flex xs12 lg4>
          <Sidebar class="py-5 my-5"/>
        </v-flex>
      </v-layout>
    </v-content>
    <Footer/>
  </v-app>
</template>



<script>
import Navbar from "./partials/Navbar";
import Footer from "./partials/Footer";
import Sidebar from "./partials/Sidebar";
export default {
  components: {
    Navbar,
    Footer,
    Sidebar
  }
};
</script>