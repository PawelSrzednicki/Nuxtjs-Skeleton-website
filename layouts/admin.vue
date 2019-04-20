<template>
  <v-app dark>
    <AdminNavbar/>
    <v-content>
      <v-container>
        <nuxt/>
      </v-container>
    </v-content>
    <AdminFooter/>
  </v-app>
</template>



<script>
import AdminNavbar from "./partials/AdminNavbar";
import AdminFooter from "./partials/AdminFooter";
export default {
  components: {
    AdminNavbar,
    AdminFooter
  }
};
</script>