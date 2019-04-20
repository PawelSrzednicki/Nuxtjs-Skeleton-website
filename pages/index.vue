<template>
  <v-container>
    <section>
      <v-parallax src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"></v-parallax>
    </section>
    <section>
      <PostList v-for="article in posts" :key="article.id" :article="article" class="my-5"/>
      <v-pagination v-model="page" :length="totalPages" @input="next"></v-pagination>
    </section>
  </v-container>
</template>
<script>
import PostList from "@/components/site/PostList";
import axios from "axios";
export default {
  components: {
    PostList
  },
  watchQuery: ["page"],
  async asyncData({ $axios, query }) {
    try {
      const page = query.page || 1;
      let { data } = await $axios.get("/articles/?page=" + page);
      return {
        posts: data.data,
        page: data.current_page,
        totalPages: data.last_page
      };
    } catch (e) {
      //  console.log(e); display errors
    }
  },
  methods: {
    next() {
      this.$router.push({ query: { page: this.page } });
    }
  }
};
</script>

