<template>
  <v-card>
    <v-card-title primary-title>
      <p class="headline">{{ article.title }}</p>
    </v-card-title>
    <v-card-text>
      <v-layout row wrap>
        <v-flex xs4 flex>
          <v-img src="https://picsum.photos/510/300?random" aspect-ratio="1"></v-img>
        </v-flex>
        <v-flex xs4 flex class="mx-3">{{ article.description }}</v-flex>
      </v-layout>
    </v-card-text>
    <v-card-actions>
      <v-btn color="success" flat nuxt :to="`${article.id}`">Read more</v-btn>
    </v-card-actions>
  </v-card>
</template>
<script>
export default {
  props: ["article"]
};
</script>
