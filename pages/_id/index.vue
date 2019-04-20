<template>
  <v-container grid-list-xl fluid>
    <v-layout mx-5>
      <v-card flat>
        <v-card-title primary-title>
          <div class="headline">{{ article.title }}</div>
        </v-card-title>
        <v-card-text>
          <v-img src="https://picsum.photos/510/300?random" aspect-ratio="2"></v-img>
          <p class="ma-5 pa-5">{{ article.description }}</p>
        </v-card-text>
      </v-card>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  async asyncData({ $axios, params }) {
    const { data } = await $axios.get(`article/${params.id}`);
    console.log(data);
    return {
      article: data
    };
  }
};
</script>