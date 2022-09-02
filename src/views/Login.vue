<template>
  <form action="" @submit.prevent="login">
    <input type="email" v-model="form.email" placeholder="email" />
    <input type="password" v-model="form.password" placeholder="password" />
    <br />
    <button>Login</button>
  </form>
</template>
<script>
import axios from "axios";
console.log(import.meta.env);
// let env = import.meta.env;
axios.defaults.withCredentials = true;
axios.defaults.baseURL = import.meta.env.VITE_API_URL; //"localhost";
export default {
  data: () => ({
    form: {
      email: "goetia@gmail.com",
      password: "password",
    },
  }),

  methods: {
    login() {
      axios.post("login").then((res) => {
        console.log(res);
      });
    },

    /* async login() {
      console.log("here go");
      await this.$store.dispatch("login", this.form);
      return this.$router.replace("/");
    }, */
  },
};
</script>
