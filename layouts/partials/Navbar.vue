<template>
  <nav>
    <v-toolbar>
      <v-toolbar-title>SimpleBlog</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-side-icon @click="drawer=!drawer" class="hidden-md-and-up"></v-toolbar-side-icon>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat v-for="item in items" :key="item.title" :to="item.link">{{ item.title }}</v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-navigation-drawer v-model="drawer" app>
      <v-list dense class="pt-0">
        <v-list-tile v-for="item in items" :key="item.title" :to="item.link">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>

          <v-list-tile-content>
            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>
<script>
export default {
  data() {
    return {
      drawer: false,
      items: [
        { title: "Home", link: "/" },
        { title: "Contact", link: "Contact" },
        { title: "About", link: "about" }
      ]
    };
  }
};
</script>