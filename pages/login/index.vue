<template>
  <v-layout justify-center align-center>
    <v-card class="elevation-10" style="flex: 0 1 400px">
      <Notification :message="error.invalid" v-if="error.invalid"/>

      <v-card-title class="headline">Log In</v-card-title>
      <v-card-text>
        <v-form method="post" @submit.prevent="login">
          <v-text-field label="Email" v-model="email" :rules="emailRules" required/>
          <v-text-field
            label="Password"
            v-model="password"
            type="password"
            :rules="passwordRules"
            required
          />
          <v-btn type="submit">submit</v-btn>
        </v-form>
      </v-card-text>
    </v-card>
  </v-layout>
</template>

<script>
import Notification from "~/components/Notification";

export default {
  layout: "clear",

  components: {
    Notification
  },

  data() {
    return {
      email: "",
      password: "",
      error: {
        message: null,
        invalid: null
      },
      emailRules: [
        v => !!v || "E-mail is required",
        v =>
          /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(v) ||
          "E-mail must be valid"
      ],
      passwordRules: [v => !!v || "Password is required"]
    };
  },

  methods: {
    async login() {
      try {
        await this.$auth.login({
          data: {
            email: this.email,
            password: this.password
          }
        });

        this.$router.push("/");
      } catch (e) {
        // this.error.message = e.response.data.message;
        this.error.invalid = e.response.data.error;
        console.log(e.response.data.message);
      }
    }
  }
};
</script>