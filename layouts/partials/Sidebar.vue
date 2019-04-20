<template>
  <v-container>
    <v-layout row wrap>
      <v-flex>
        <About class="mb-5"/>
        <Contact class="my-5"/>
      </v-flex>
    </v-layout>
  </v-container>
</template>
<script>
import About from "@/components/site/AboutCard";
import Contact from "@/components/site/ContactCard";
export default {
  components: {
    About,
    Contact
  }
};
</script>
<style>
</style>

