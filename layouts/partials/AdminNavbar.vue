<template>
  <nav>
    <v-toolbar app fixed clipped flat>
      <v-toolbar-side-icon @click.stop="mini = !mini"></v-toolbar-side-icon>
      <v-toolbar-title>Title</v-toolbar-title>
    </v-toolbar>

    <v-navigation-drawer v-model="drawer" :mini-variant.sync="mini" app>
      <v-toolbar color="transparent" flat>
        <v-list class="pa-0">
          <v-list-tile avatar>
            <v-list-tile-avatar>
              <img src="https://vuetifyjs.com/apple-touch-icon-180x180.png">
            </v-list-tile-avatar>

            <v-list-tile-content>
              <v-list-tile-title>
                <span>
                  <img
                    src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/88e41ea5-31ab-4219-afa2-fafd7461d00f/d424vhr-8a05a5d7-6b96-4303-89a1-16b5a2020f37.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzg4ZTQxZWE1LTMxYWItNDIxOS1hZmEyLWZhZmQ3NDYxZDAwZlwvZDQyNHZoci04YTA1YTVkNy02Yjk2LTQzMDMtODlhMS0xNmI1YTIwMjBmMzcucG5nIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.3q9aMP7iSc1Y9HiPQg6CQ3exmlWAqq2iWD-jDUbB2bA"
                    width="128px"
                    height="100%"
                  >
                </span>
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-toolbar>
      <v-list class="pt-0" dense>
        <v-divider></v-divider>

        <v-list-tile v-for="item in items" :key="item.title" :to="item.route">
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
      drawer: true,
      items: [
        { title: "Home", icon: "dashboard", route: "/admin" },
        { title: "Articles", icon: "question_answer", route: "/admin/articles" }
      ],
      mini: true,
      right: null
    };
  }
};
</script>
